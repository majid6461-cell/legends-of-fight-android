# Test report — 2026-11-03

## Verification performed in this delivery environment

| Check | Result | Notes |
|---|---|---|
| Project folder and required source files | PASS | Godot project, scenes, scripts, icon, Android preset, README, and CI workflow created. |
| Roster metadata | PASS | 12 unique fighter definitions are present in `scripts/roster.gd`. |
| Arena metadata | PASS | 8 arena definitions are present in `scripts/roster.gd`. |
| Workflow YAML syntax | PASS | Parsed successfully with a YAML parser. |
| GDScript delimiter/string sanity check | PASS | Brackets and quoted strings are balanced; this is not a Godot parser run. |
| Source ZIP integrity | PASS | `unzip -t` completed with no archive errors. |
| Feature implementation review | PARTIAL | Menu/mode selection, fighters, controls, hit/hurt query, AI, round flow, and tournament flow are implemented in GDScript; runtime behavior remains unverified. |
| GDScript parse / Godot headless import | NOT RUN | Godot is not installed in the current execution environment, and external downloads are unavailable here. |
| APK export | NOT RUN | Android SDK, export templates, and Godot CLI are not installed in this environment. |
| APK install / emulator smoke test | NOT RUN | No Android emulator or ADB is available. |
| GitHub repository creation | BLOCKED | The connected GitHub integration exposes repository/file operations but not repository creation; the connected account had no visible repositories in the listing returned for this session. |

## Required next validation

1. Create an empty GitHub repository named `legends-of-fight-android` under the intended account.
2. Upload/push this project to the repository default branch.
3. Run the `Build Android APK` workflow manually.
4. Fix any Godot parser/import or export errors reported by that run.
5. Install the artifact on at least one Android device and test single-player, local two-player, tournament, practice, touch input, and orientation.

**No claim is made that an APK exists or that the game has passed runtime/device testing.**

## Final verification update — 2026-11-03

The initial local environment did not contain Godot or the Android SDK. After the repository was connected, the GitHub Actions workflow was run and corrected. The fourth run completed successfully:

- Run: https://github.com/majid6461-cell/legends-of-fight-android/actions/runs/41624645979
- Godot: 4.7.2 stable
- Project import: PASS
- Smoke test: PASS (12 unique fighter entries, 8 arena entries)
- Android export: PASS
- Package metadata: com.legends.fight, version 0.1.0, min SDK 24, target SDK 36
- Artifact ID: 13225740230
- APK size: 28,448,164 bytes
- APK SHA-256: 1ff769bd2de458b381d60f5f4fdde900858e0c81fef37fb0c29f8e46f392921c

The exported APK was downloaded back from GitHub and its ZIP integrity check passed. It has NOT been installed or run on a physical phone or emulator. It is debug-signed; production distribution requires a private release keystore.
