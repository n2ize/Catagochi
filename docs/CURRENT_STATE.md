# Aktueller Entwicklungsstand (Current State)

## Stand: Initialisierung & Environment-Setup (Phase 0)

### Was bisher erledigt wurde:
- Projektbriefing und Anforderungen analysiert.
- Technische Architektur und Schichtenmodell definiert.
- Projektgedächtnis (`AGENTS.md`, `docs/*`) initialisiert und comittet.
- Git-Repository aufgesetzt mit `.gitignore`.
- Entwicklungsumgebung eingerichtet:
  - Microsoft Visual Studio 2022 C++ Build Tools (MSVC) verifiziert.
  - Rust Toolchain (`rustc 1.100.0`, `cargo 1.100.0`) erfolgreich installiert.

### Nächste Schritte:
1. Entscheidung über Frontend-Setup (Vite-Dev-Server für Hot-Reload vs. No-Bundler Vanilla Static).
2. Tauri 2 Projektstruktur initialisieren.
3. Erstes Widget-Fenster konfigurieren (Always-on-Top, rahmenlos, feste Abmessungen).
