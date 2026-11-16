# Project Brief: Catagotchi

## Projektidee
- Entwicklung einer virtuellen Katze im Stil eines Tamagotchis.
- Grundlage sind echte Fotos der eigenen Katze.
- Ermöglicht es, die Katze häufiger auf dem Desktop zu sehen und mit ihr zu interagieren.
- Langfristig anpassbar, sodass Freunde ihre eigenen Haustiere einbinden können.
- Anspruchsvolles persönliches Software-Engineering- und GitHub-Portfolio-Projekt.

## Zielplattform & Eigenschaften
- **Betriebssystem**: Primär Windows (Desktop).
- **Formfaktor**: Kompaktes Desktop-Widget (unten rechts platzierbar).
- **Verhalten**: Optional Always-on-Top, rahmenlos, unaufdringlich, minimaler Ressourcenverbrauch im Hintergrund.
- **Zukunft**: System Tray, Autostart, Multi-Monitor-Unterstützung.

## Technologie-Stack
- **Frontend**: HTML5, CSS3, Vanilla JavaScript (ES6+). Keine Frameworks (kein React/Vue), kein TypeScript.
- **Desktop Framework**: Tauri 2.
- **Backend / Engine**: Rust.
- **Datenbank**: SQLite.
- **Versionskontrolle**: Git & GitHub.

## MVP-Funktionsumfang
- Eine Katze mit eigenem Foto.
- Drei Kernattribute: **Hunger**, **Glück**, **Energie** (0-100).
- Drei Interaktionen:
  - Füttern (reduziert Hunger)
  - Spielen (erhöht Glück, kostet Energie)
  - Schlafen (regeneriert Energie)
- Zeitbasierte Veränderung (Decay).
- Persistenz via SQLite (Zustand bleibt nach Schließen erhalten).
- Offline-Zeit-Simulation: Berechnung der Differenz zwischen Schließen und erneutem Öffnen.
