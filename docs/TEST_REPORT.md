# Final test report — 2026-11-03

## Latest successful CI run

- Workflow: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41625155209
- Commit: e4bc89f910100245905b6004619955465945a42e
- Godot: 4.7.2.stable.official.ed1daf0bf
- Project import and GDScript parsing: PASS; no script parse errors were emitted by the import step.
- Smoke test: PASS; 12 fighter profiles and 8 arenas validated. Main and fighter game scripts are loaded through preloads so parse errors fail the test.
- Android export: PASS.
- Package metadata: com.legends.fight, version 0.1.0, minimum SDK 24, target SDK 36.
- Artifact ID: 13225029167.
- APK size: 28,448,164 bytes.
- APK SHA-256: 765508775c6c876956d21a291ec318322e9a4ca0b0c51d061bdc0e81602aaa6c.
- APK archive integrity: PASS; the downloaded APK ZIP passed unzip -t with no compressed-data errors.

## Not yet tested

- Installation and launch on a physical Android device or emulator have not been performed.
- Manual playthrough of every mode, long-duration stability, thermal behaviour and FPS across multiple phone models have not been tested.

## Scope

This is an MVP. The 12 fighters and 8 arenas are selectable procedural low-poly prototypes, not a commercial Tekken-scale production. Professional skeletal animation, dedicated sound/music, persistent unlock progression and device-level gameplay validation remain future work.

The APK is debug-signed. A production/Google Play release needs a private release keystore and a separately configured signing workflow.
