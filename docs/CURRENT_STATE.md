# Aktueller Entwicklungsstand (Current State)

## Stand: Start von Phase 1 (Desktop Widget & Window Controls)

### Was bisher erledigt wurde:
- Projektbriefing und Anforderungen analysiert.
- Technische Architektur und Schichtenmodell definiert.
- Projektgedächtnis (`AGENTS.md`, `docs/*`) initialisiert.
- Git-Repository aufgesetzt, mit GitHub verknüpft (`main`) und synchronisiert.
- Entwicklungsumgebung eingerichtet:
  - Microsoft Visual Studio 2022 C++ Build Tools (MSVC) verifiziert.
  - Rust Toolchain (`rustc 1.100.0`, `cargo 1.100.0`) installiert.
- Tauri 2 Projektstruktur mit Vanilla JS und schlankem Vite-Entwicklungsserver aufgesetzt:
  - Widget-Größe: 260x360 px, `decorations: false`, `alwaysOnTop: true`.
  - Backend `cargo check` erfolgreich (alle Crates aufgelöst & kompiliert).
  - Portfolio-gerechtes `README.md` erstellt.

### Nächste Schritte (Phase 1):
1. Erstes Starten der Desktop-Anwendung via `npm run tauri dev`.
2. Fenster-Interaktion testen: Da das Fenster rahmenlos ist, benötigen wir:
   - Eine Drag-Region, um das Fenster beliebig auf dem Desktop zu verschieben.
   - Kleine dezente Controls (z. B. Minimieren / Schließen).
3. Danach Übergang zu Phase 2 (UI-Aufbau mit Katzenfoto und Attributbalken).
