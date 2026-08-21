# ZKR Changelog

## 1.3.0
- Fix corrupted UTF-8 text across 374 source files (restored em dashes, box-drawing characters, CJK text, prompts and comments)
- Release notes are now served from the zkr-data repository
- ZKR identity: the agent now presents itself as ZKR powered by Z Code models in all conversations
- Commit and PR attribution now shows Z Code model names instead of internal model IDs

## 1.2.8
- Slugify the x-opencode-project header for Zen

## 1.2.7
- Install to C:\Program Files\ZKR and add that path to the user PATH
- Fix zkr-setup.exe naming and auto-close a running zkr on update
- Raise the default goal continuation cap to 1000 turns

## 1.2.6
- Rebrand to ZKR and wire the UI updater to GitHub releases

## 1.2.5
- Ship per-platform installers in releases (setup.exe, .deb, .pkg)
- Add ZKR branding to installers (Linux .desktop + icon, macOS .app bundle with .icns)
- Embed version at build time and verify binaries in CI

## 1.2.4
- Hide real model IDs from user-facing Z Code errors

## 1.2.3
- Fix installer asset names and provide dist\zkr.exe for Inno Setup in CI

## 1.2.2
- Make zkr update work on Windows (rename strategy)
- Fall back to a pure-TS directory walk for @-mentions

## 1.2.1
- Strip image payloads from tool_results to avoid context blowups

## 1.2.0
- Embed a read-only auto-update token in release binaries
- Report the real version in compiled binaries
- Preserve thinking blocks for Z Code (avoid reasoning_content round-trip 400)
- Inject reasoning_content on every assistant turn for Zen thinking models

## 1.1.1
- Harden Zen API retry handling and add streaming tests
- Send the opencode User-Agent to the Zen gateway and raise stream timeouts

## 1.1.0
- Add GitHub Releases auto-update system (zkr update)
- Use gh api for private repo support in auto-update
- Remove the "Opus now defaults to 1M context" notice

## 1.0.0
- Initial ZKR CLI release
- Dynamic ZCode model resolution
- Autonomous goal system (/goal, goal_get, update_goal)
- Preload ZCode session data at startup and parallelize fetches