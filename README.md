# Dino Run

Dino Run is a 2D side-scrolling endless runner built with Flutter and the Flame game engine. The player controls a dinosaur that jumps over (or between) incoming enemies while score increases over time and health decreases on collisions.

This project demonstrates practical game-loop engineering in Flutter: component-based gameplay logic, collision handling, layered UI overlays, audio controls, and local persistence for player progress and settings.

## Screenshots

Screenshots and GIF demos will be added here.
Demo video: [Watch gameplay demo](assets/demo/dino_run%20beta%201.0.mp4)

## Key Features

- Endless-runner gameplay with tap-to-jump controls.
- Multiple enemy types with randomized spawning and movement behavior.
- Collision-based life system and game-over flow.
- Real-time HUD showing current score, high score, pause control, and lives.
- Main menu, pause menu, game-over menu, and settings overlay screens.
- Persistent high score and audio settings (music/SFX) using local storage.

## Architecture

The project uses a `FlameGame` core (`DinoRun`) for the game loop and world state, with gameplay entities implemented as Flame components (`Dino`, `Enemy`, `EnemyManager`). UI is separated into Flutter overlays (`MainMenu`, `Hud`, `PauseMenu`, `GameOverMenu`, `SettingsMenu`) attached through `GameWidget`.

State that must update UI reactively is modeled with `ChangeNotifier` classes (`PlayerData`, `Settings`) and consumed via `provider`/`Selector` in overlays. Data is persisted through Hive adapters, while an `AudioManager` singleton encapsulates background music and sound effects behavior.

## Tech Stack

### Framework and Language
- Flutter
- Dart

### Architecture and State Management
- Flame component-based game architecture
- Flutter overlays via `GameWidget.overlayBuilderMap`
- `provider` with `ChangeNotifier` and `Selector`

### Backend and Data
- Hive for local persistence (player stats and settings)
- `path_provider` for platform storage paths

### UI and Experience
- Flame parallax background
- Sprite-sheet animations and collision hitboxes
- `flame_audio` for BGM and SFX

## What This Project Demonstrates

- Building a real-time game loop and entity system on top of Flutter.
- Combining Flame gameplay components with Flutter UI overlays cleanly.
- Managing persistent local state (high score, settings) in a production-style way.

## Getting Started

1. Install Flutter SDK and verify setup with `flutter doctor`.
2. From the project root, install dependencies with `flutter pub get`.
3. Run the app with `flutter run`.
