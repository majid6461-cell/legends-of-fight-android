# LEGENDS OF FIGHT — افسانه‌های مبارزه

A mobile-first, original 3D fighting-game MVP built with **Godot 4.7.2** and GDScript. The visuals are generated procedurally from low-poly 3D primitives, so the project does not depend on copyrighted character models, textures, logos, or music.

> **Current delivery status:** playable prototype source project + Android export preset + GitHub Actions workflow. An APK has **not** yet been built or emulator-tested in this environment. See `docs/TEST_REPORT.md`.

## Implemented in this MVP

- 12 original fighter profiles with different stats, palettes, styles, and special-move names.
- 8 selectable arenas, each with a distinct procedural 3D color palette and environment dressing.
- Character selection for both player slots and arena selection.
- Single-player versus AI with Easy / Normal / Hard decision behavior.
- Two-player local mode with independent keyboard mappings and separate touch-control panels on Android.
- Tournament mode with 10 successive opponents and rising difficulty.
- Practice mode with a passive opponent.
- Health and energy meters, block, jump, light punch, heavy strike, kick, special move, ultimate, hit reactions, and a round timer.
- Sphere-query attack hitboxes and Area3D hurtboxes.
- Persian-first menus and a basic English-language option.
- Low / Medium / High graphics quality setting (controls arena shadow/light quality).
- Landscape Android configuration and an automated APK artifact workflow.

## Important scope note

This is a functional **MVP**, not a finished commercial Tekken-scale production. Fighter models are original procedural low-poly placeholders, and animation is procedural rather than a full motion-captured skeletal animation set. Audio assets, advanced combo buffering, rollback/netcode, online play, and a polished cinematic presentation are not included in this first build. The 12 roster entries are currently selectable; the unlock field is roster metadata for a future progression pass and is not yet enforced by a save/unlock economy.

## Project structure

```text
legends-of-fight-android/
├── .github/workflows/android.yml
├── assets/icon.svg
├── scenes/main.tscn
├── scripts/main.gd
├── scripts/fighter.gd
├── scripts/roster.gd
├── characters/
├── animations/
├── environments/
├── textures/
├── audio/
├── ui/
├── android/
├── docs/TEST_REPORT.md
├── project.godot
└── export_presets.cfg
```

The empty folders are reserved for future imported resources. The current MVP creates the fighters, arena geometry, HUD, and controls at runtime.

## Run in Godot

1. Install Godot **4.7.2 stable**.
2. Open the project folder (`project.godot`) in Godot.
3. Let the editor import the project.
4. Press **F6/F5** or use **Project → Run**.
5. Select a game mode, two fighters, and an arena.

### Desktop controls

| Action | Player 1 | Player 2 |
|---|---|---|
| Move | A / D | ← / → |
| Jump | W | ↑ |
| Block | S | ↓ |
| Light punch | F | K |
| Heavy strike | G | L |
| Kick | V | , |
| Special | H | I |
| Ultimate | J | O |

The Special requires 30 energy and the Ultimate requires 100 energy. Energy is gained by landing and receiving hits.

### Android touch controls

The game is configured for landscape orientation. On Android, touch controls appear after starting a match. In local two-player mode, each player receives a separate panel on their half of the screen.

## Build the APK locally

1. Install Java 17 and the Android SDK.
2. In Godot Editor Settings → Export → Android, set the Java SDK Path and Android SDK Path.
3. Download/install the export templates matching Godot 4.7.2.
4. From the project folder, run:

```bash
godot --headless --editor --import --path . --quit
godot --headless --path . --export-debug "Android" build/LegendsOfFight.apk
```

The export preset targets **arm64-v8a** and uses the package ID `com.legends.fight`.

## Build with GitHub Actions

The workflow `.github/workflows/android.yml` runs when a `v*` tag is pushed or manually from the Actions tab. It downloads the matching Godot editor and export templates, sets up Java/Android SDK, imports the project, exports a debug APK, checks the APK package metadata, and uploads `LegendsOfFight.apk` as a workflow artifact.

To publish a version:

```bash
git tag v0.1.0
git push origin v0.1.0
```

Then open **GitHub → Actions → Build Android APK** and download the artifact from the completed run. This workflow currently produces a **debug-signed APK** for testing; a Play Store release needs a private release keystore stored as GitHub Actions secrets and a separate signed release workflow.

## Current limitations / next development pass

- No final-quality authored 3D meshes, skeletal animation clips, professional sound/music, or cinematic effects yet.
- No persistent save system, currency, character unlocking, or tournament record storage yet.
- The quality setting currently changes stage lighting/shadows; it does not yet change texture resolution or render scale.
- No online multiplayer. Local two-player is supported.
- Always test touch layout and device performance on the target phone before public release.

## License

Project source is provided for personal development and modification. All code and procedural placeholder art in this starter project are original to this project. Add third-party assets only after checking their licenses.

## Latest build status — v0.1.0 (2026-11-03)

The Android export completed successfully with Godot 4.7.2. The project was imported headlessly, the roster/arena smoke test passed, and the APK package metadata was verified (com.legends.fight, version 0.1.0, min SDK 24, target SDK 36). The debug APK was uploaded as a GitHub Actions artifact.

Build run: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41624645979

The APK is debug-signed and has not been installed/tested on a physical device or emulator. A production release requires a private release keystore.


## Final verification — 2026-11-03 (latest run)

The latest CI run succeeded: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41625155209. Godot 4.7.2 project import and GDScript parsing, the 12-fighter/8-arena smoke test, Android export, package metadata inspection, and artifact upload passed. APK package: com.legends.fight, version 0.1.0, min SDK 24, target SDK 36. Artifact ID: 13225029167.

The APK is debug-signed. Installation and gameplay on a physical phone or emulator have not yet been performed. See docs/TEST_REPORT.md for details and SHA-256.
