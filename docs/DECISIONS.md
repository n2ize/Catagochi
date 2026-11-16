# Architecture Decision Records (ADR)

## ADR-001: Vanilla JavaScript statt Frontend-Frameworks
- **Datum**: 2026-11-16
- **Status**: Akzeptiert
- **Kontext**: Für das Projekt sollte ein Frontend-Stack gewählt werden.
- **Entscheidung**: Verwendung von reinem HTML5, CSS3 und Vanilla JavaScript ohne React, Vue oder TypeScript.
- **Begründung**:
  1. Das Projekt dient als didaktisches Fundament, um grundlegende JavaScript-Konzepte (DOM, Event-Loop, Async/Await) tiefgehend zu verstehen.
  2. Ein Desktop-Widget dieser Größe benötigt keinen Framework-Overhead.
  3. Schnellere Build-Zeiten und minimaler Speicherverbrauch.

## ADR-002: Tauri 2 statt Electron
- **Datum**: 2026-11-16
- **Status**: Akzeptiert
- **Kontext**: Ein Desktop-Framework wird benötigt, um Webtechnologien auf Windows lauffähig zu machen.
- **Entscheidung**: Einsatz von Tauri 2 mit Rust.
- **Begründung**:
  1. Electron bündelt eine vollständige Chromium-Instanz und Node.js (~150MB+ RAM-Verbrauch).
  2. Tauri nutzt die native Windows WebView2 (~20–40MB RAM-Verbrauch) – ideal für ein unauffälliges Hintergrund-Widget.
  3. Ermöglicht das Erlernen von Rust für systemnahe Aufgaben.

## ADR-003: Rust als autoritative Spiellogik (Single Source of Truth)
- **Datum**: 2026-11-16
- **Status**: Akzeptiert
- **Kontext**: Wo sollen Attributwerte (Hunger, Energie, Zeit-Decay) berechnet werden?
- **Entscheidung**: Die Simulationslogik liegt vollständig im Rust-Backend.
- **Begründung**:
  1. Windows drosselt Hintergrund-WebViews (JavaScript-Timer wie `setInterval` stoppen oder verlangsamen sich).
  2. Das Rust-Backend garantiert gleichmäßige Ticks und korrekte Offline-Zeitberechnung vor dem Rendern.
