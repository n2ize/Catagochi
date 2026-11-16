# Technische Architektur

## Übersicht
Catagotchi verwendet eine strikte Trennung zwischen Präsentationsschicht (Frontend in Tauri WebView) und autoritativer Spiellogik/Persistenz (Backend in Rust).

```
+-------------------------------------------------------+
|                 Frontend (WebView)                    |
|  - HTML5 / CSS3 / Vanilla JavaScript                  |
|  - Reine Präsentationsschicht (View)                  |
|  - Rendert UI, Katzenfotos, Balken, Animationen       |
|  - Sendet Benutzeraktionen via Tauri IPC               |
+--------------------------▲----------------------------+
                           │  invoke('command') / Events
                           ▼
+-------------------------------------------------------+
|                   Backend (Rust)                      |
|  - Single Source of Truth (Game State)                |
|  - State Machine & Decay-Berechnung                   |
|  - Offline-Deltaberechnung (Zeitstempel)              |
|  - Desktop-Window-Management (Position, Always-on-Top)|
+--------------------------▲----------------------------+
                           │  SQL Queries
                           ▼
+-------------------------------------------------------+
|                    SQLite DB                          |
|  - pet_state (hunger, happiness, energy, last_tick)   |
|  - app_settings (window_x, window_y)                  |
+-------------------------------------------------------+
```

## Schichtenmodell

### 1. Frontend (Vanilla JS, HTML5, CSS3)
- **Verantwortung**: Präsentation und Benutzereingaben.
- **Module**:
  - `api.js`: Kapselt Aufrufe an `window.__TAURI__.core.invoke`.
  - `ui.js`: DOM-Manipulation (Aktualisierung der Balken, Bildwechsel je nach Stimmung).
  - `app.js`: Einstiegspunkt, Event-Listener für Buttons und Drag-Region.

### 2. Backend (Rust & Tauri 2)
- **Verantwortung**: Autoritative Logik, State Machine, Zeitberechnung, Desktop-Integration.
- **Module**:
  - `state.rs`: `PetState`-Struct (Hunger, Happiness, Energy, LastTick).
  - `simulation.rs`: Verfallslogik (Decay-Ticks) und Offline-Aufholberechnung.
  - `db.rs`: SQLite-Verbindung (`rusqlite`), Tabellen-Erstellung, Laden/Speichern.
  - `lib.rs` / `main.rs`: Tauri IPC-Command-Handler (`get_pet_state`, `feed`, `play`, `sleep`).

### 3. IPC-Schnittstelle (Inter-Process Communication)
Kommunikation erfolgt asynchron über Tauri Commands:
- `get_pet_state() -> PetState`: Liefert aktuellen Zustand an das Frontend.
- `feed_pet() -> PetState`: Verarbeitet Füttern, validiert und gibt neuen Zustand zurück.
- `play_with_pet() -> PetState`: Verarbeitet Spielen.
- `sleep_pet() -> PetState`: Schickt Katze schlafen / weckt sie auf.
