# ZKR Changelog

## 1.3.1
- Product URL is now https://zkrweb.vercel.app/
- Fresh installs no longer require an account — works with no account (OAuth disabled by default for future account system)
- Improved onboarding: new welcome intro (no account required), theme → security → terminal flow with no provider leak
- Terminal welcome animation replaced — ZKR Code ASCII with tagline `powered by Z Code • zkrweb.vercel.app` and new app icon
- Fix per-model context windows for Z Code — auto-compact now respects 1M vs 256K/200K from `zcode-ranking.json` (no more premature compact at 265K for 1M models)
- `zkr update` now uses https://zkrweb.vercel.app (no GitHub token required) — version check and binary download via Vercel proxy (server holds `GITHUB_TOKEN`)

## 1.3.0
- Fix corrupted UTF-8 text across 374 source files (restored em dashes, box-drawing characters, CJK text, prompts and comments)
- Release notes are now served from the zkr-data repository
- ZKR identity: the agent now presents itself as ZKR powered by Z Code models in all conversations
- Commit and PR attribution now shows Z Code model names instead of internal model IDs
- /goal autonomy: transient API errors (rate limits, capacity, timeouts) no longer kill the goal — the loop backs off and continues; only repeated failures (5+) or terminal errors (auth/billing) stop it
- /goal autonomy: internal tool aborts no longer stop the loop — only explicit user takeover (Esc, interrupt) pauses auto-continuation
- /goal: stronger per-turn work expectations so the agent keeps chaining tool calls instead of stopping after one or two steps

## 1.2.8
- Slugify the project header

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
- Inject reasoning_content on every assistant turn for thinking models

## 1.1.1
- Harden API retry handling and add streaming tests
- Send the User-Agent to the gateway and raise stream timeouts

## 1.1.0
- Add GitHub Releases auto-update system (zkr update)
- Use gh api for private repo support in auto-update
- Remove the "Opus now defaults to 1M context" notice

## 1.0.0
- Initial ZKR CLI release
- Dynamic ZCode model resolution
- Autonomous goal system (/goal, goal_get, update_goal)
- Preload ZCode session data at startup and parallelize fetches
