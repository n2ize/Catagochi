# Entwicklungs-Roadmap

## Phase 0: Vorbereitung & Setup (Abgeschlossen)
- [x] Projektidee & Briefing analysieren
- [x] Dokumentationsstruktur (`AGENTS.md`, `docs/*`) anlegen
- [x] Git-Repository initialisieren & mit GitHub verknüpfen
- [x] Rust & C++ Build Tools installieren und verifizieren
- [x] Tauri 2 Projekt mit Vanilla JS & Vite Dev-Server aufsetzen
- [x] Initiales Widget-Fenster konfigurieren (260x360, rahmenlos, Always-on-Top)

## Phase 1: Das Tauri 2 Desktop-Widget & Window-Controls (Aktuell)
- [ ] Erstes lokales Starten und Fenster-Verhalten testen
- [ ] Drag-to-Move für rahmenlose Fenster einrichten (`data-tauri-drag-region`)
- [ ] Minimiere / Schließen Buttons im Widget (da rahmenlos)

## Phase 2: Frontend-Prototyp (Vanilla Web)
- [ ] HTML-Grundstruktur (Katzenfoto, 3 Balken, 3 Buttons)
- [ ] Modernes CSS-Styling für das Desktop-Widget
- [ ] Lokale UI-Updates (Mock-Buttons in JS)

## Phase 3: Rust State & IPC
- [ ] `PetState`-Struct in Rust
- [ ] Erste Tauri Commands (`get_pet_state`, `feed_pet`, `play_with_pet`, `sleep_pet`)
- [ ] Anbindung im Frontend via `invoke`

## Phase 4: Zeitbasierte Simulation & Offline-Decay
- [ ] Rust Ticking-Engine für kontinuierlichen Verfall
- [ ] Offline-Berechnung beim App-Start anhand von SQLite-Zeitstempeln

## Phase 5: Persistenz mit SQLite
- [ ] SQLite Tabellenschema
- [ ] Automatisches Speichern bei Interaktionen & beim Schließen

## Phase 6: Polish & Portfolio
- [ ] Dynamischer Bildwechsel je nach Katze-Status
- [ ] Sound- oder Animationseffekte
- [ ] GitHub README mit Architekturdiagramm, Screenshots und Setup-Guide
