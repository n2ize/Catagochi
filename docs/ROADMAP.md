# Entwicklungs-Roadmap

## Phase 0: Vorbereitung & Setup (In Arbeit)
- [x] Projektidee & Briefing analysieren
- [x] Dokumentationsstruktur (`AGENTS.md`, `docs/*`) anlegen
- [x] Git-Repository initialisieren
- [x] Rust & C++ Build Tools installieren und verifizieren
- [ ] Tauri 2 CLI & Projekt initialisieren

## Phase 1: Minimales Tauri 2 Desktop-Widget
- [ ] Tauri-Projekt aufsetzen
- [ ] Fensterkonfiguration: rahmenlos (`decorations: false`), `alwaysOnTop: true`, Größe ca. 260x340
- [ ] Drag-Region testen (`data-tauri-drag-region`)

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
