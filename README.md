# Catagotchi 🐱

A lightweight, unobtrusive desktop Tamagotchi widget featuring real cat photos, built for Windows using **Tauri 2**, **Rust**, and **Vanilla JavaScript**.

![Architecture](https://img.shields.io/badge/Architecture-Tauri%202%20%2B%20Rust-orange)
![Frontend](https://img.shields.io/badge/Frontend-Vanilla%20JS%20%2B%20CSS3-yellow)
![Database](https://img.shields.io/badge/Storage-SQLite-blue)
![Platform](https://img.shields.io/badge/Platform-Windows-blue)

## Project Overview

Catagotchi is a personal software engineering and portfolio project designed to explore systems programming, desktop window integration, and event-driven architectures:
- **Desktop Widget**: Sits subtly on the desktop (frameless, compact, `Always on Top`).
- **Real Pet Photos**: Visual states change dynamically based on the cat's mood and needs.
- **Time-Based Simulation**: Continuous decay of attributes (Hunger, Happiness, Energy) with offline-time catch-up calculated upon launch.
- **Lean Architecture**: Pure HTML5/CSS3/Vanilla JS frontend with 0 heavy frameworks, powered by a native Rust backend and SQLite persistence.

## Architecture & Technology Stack

```
+-------------------------------------------------------+
|                 Frontend (WebView2)                   |
|  - HTML5 / CSS3 / Vanilla JavaScript (ES6+)           |
|  - Presentation, CSS animations & user input          |
|  - Fast live-reloading during development via Vite    |
+--------------------------▲----------------------------+
                           │  Tauri IPC (invoke / events)
                           ▼
+-------------------------------------------------------+
|                   Backend (Rust)                      |
|  - Authoritative Game State Machine                   |
|  - Time calculation & continuous decay simulation     |
|  - Native OS window controls (frameless, always on top)|
+--------------------------▲----------------------------+
                           │  SQLite
                           ▼
+-------------------------------------------------------+
|                     SQLite DB                         |
|  - Persistent pet state & timestamps                  |
|  - Window position & user settings                    |
+-------------------------------------------------------+
```

## Documentation

The project maintains structured documentation in the `docs/` folder:
- [PROJECT_BRIEF.md](docs/PROJECT_BRIEF.md): Core vision and feature scope.
- [ARCHITECTURE.md](docs/ARCHITECTURE.md): Deep-dive into IPC interfaces and component boundaries.
- [CURRENT_STATE.md](docs/CURRENT_STATE.md): Current development milestone and active tasks.
- [DECISIONS.md](docs/DECISIONS.md): Architecture Decision Records (ADRs).
- [ROADMAP.md](docs/ROADMAP.md): Milestone plan from Phase 0 to Phase 6.

## Development Setup

### Prerequisites
- [Node.js](https://nodejs.org/) (v18+) & npm
- [Rust & Cargo](https://rustup.rs/) (stable msvc)
- Microsoft C++ Build Tools (Visual Studio 2022)

### Running Locally
```bash
# Install frontend dev dependencies
npm install

# Run in development mode (starts Vite + Tauri Desktop Widget)
npm run tauri dev
```
