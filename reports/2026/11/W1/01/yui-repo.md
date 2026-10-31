---
source: "yui-repo"
date: "2026-11-01"
generated_at: "2026-11-01T08:00:12+09:00"
summary: "YUI repository: 36 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-31T23:00:12Z"}
---

# YUI repository: 36 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [Windows run of the plugin host and catalog install before v0.6.0](<https://github.com/yw0nam/YUI/issues/1701>)
   issue · 2026-10-31T14:51:49Z
   Part of #1657 ## Question Before v0.6.0, run the plugin host and catalog install on Windows x64 for real. Today every Windows path of the host compiles in CI but has never run (#1665: the job object, `CREATE_NO_WINDOW`, the process-tree kill), and Mark-of-the-Web on files the ap…
2. [chore: catalog browser v0.1.1](<https://github.com/yw0nam/YUI/pull/1762>)
   pull_request · 2026-10-31T14:49:41Z
   ## Summary The checks do not start on a PR opened by GITHUB_TOKEN; before merging, run `gh pr close <n> && gh pr reopen <n>` once. Lists browser 0.1.1 in the plugin catalog, from the release https://github.com/yw0nam/YUI/releases/tag/plugin-browser-v0.1.1. ## Related issues N/A …
3. [\[bug\] The character's feet sit 12 to 22 px below the work-area bottom after a floor landing, and no fall_landed line is logged](<https://github.com/yw0nam/YUI/issues/1530>)
   issue · 2026-10-31T14:02:25Z
   ## Symptoms After a floor landing, the character's lowest opaque pixel row sits below the work-area bottom, at the default window size and at a restored size alike. No `fall_landed` line is logged in any launch, so the landing cannot be checked from the log. ## Steps to reproduc…
4. [fix: the feet anchor stands the soles' near edge on the floor line](<https://github.com/yw0nam/YUI/pull/1761>)
   pull_request · 2026-10-31T14:02:23Z
   ## Summary After a floor landing the character's soles sat a few pixels below the work-area bottom. The feet anchor projected the model box's bottom point at the box's middle depth. The perspective camera sits above the floor (`camera.position.y` 0.82 at the default fit), so a f…
5. [\[bug\] The browser plugin's screenshot timed out on Windows until the ego lite window was cycled](<https://github.com/yw0nam/YUI/issues/1749>)
   issue · 2026-10-31T14:00:21Z
   ## Symptoms On Windows, `await screenshot(page)` in a `browser` call failed after 15 s with `CdpRequestTimeoutError: CDP request timed out: Page.captureScreenshot`. The rest of the script ran. The cause is not known yet, and this one failure may be ego lite's and not YUI's. Foun…
6. [\[bug\] On Windows, disabling the browser plugin or quitting YUI closes an ego lite the plugin started](<https://github.com/yw0nam/YUI/issues/1750>)
   issue · 2026-10-31T14:00:19Z
   ## Symptoms On Windows, when the `browser` plugin's call is what starts ego lite, disabling the plugin or quitting YUI closes ego lite with it. ego lite is the user's own browser, and it can be their default browser. `plugins/browser/README.md` § Task-space lifetime says a task …
7. [fix: browser starts ego lite outside the job and bounds a stalled screenshot](<https://github.com/yw0nam/YUI/pull/1754>)
   pull_request · 2026-10-31T14:00:18Z
   ## Summary Two fixes in the `browser` plugin, released as 0.1.1. **ego lite outlives the plugin on Windows (#1750).** Before each script call, `browser.exe` runs `ego-browser nodejs -e 0` with `CREATE_BREAKAWAY_FROM_JOB` and waits for it. That CLI call starts ego lite when it is…
8. [\[bug\] On Windows, updating or removing a plugin during a running call leaves its files behind](<https://github.com/yw0nam/YUI/issues/1748>)
   issue · 2026-10-31T13:59:48Z
   ## Symptoms On Windows, updating or removing a plugin while one of its tool calls runs leaves files on disk. - An update leaves the old version folder with `bin/<id>.exe` in it. Only a warning in the app log says so. The folder stays until the plugin is removed. - A removal can …
9. [fix: the host owns each server's Windows job, and a stop waits for the process](<https://github.com/yw0nam/YUI/pull/1756>)
   pull_request · 2026-10-31T13:59:47Z
   ## Summary On Windows, stopping a plugin server did not wait for it, and a server still starting was not stopped at all. Updating or removing a plugin mid-call left its files behind. This PR also gives the job the limit that #1750's plugin half needs. ``` mcp_host/ tree.rs new: …
10. [\[feature\] CI fails a PR that changes README.md without README.ja.md](<https://github.com/yw0nam/YUI/issues/1759>)
   issue · 2026-10-31T13:29:14Z
   ## Work description `README.md` and `README.ja.md` carry the same content in two languages. Nothing checks that they move together. On "Remove the bed scene and every bed path" (#1752, PR #1757), the docs commit 7537ac9c deleted the bed credits from `README.md` only; `README.ja.…
11. [ci: fail a PR that changes one README language without the other](<https://github.com/yw0nam/YUI/pull/1760>)
   pull_request · 2026-10-31T13:29:13Z
   ## Summary A PR that changes `README.md` or `README.ja.md` but not the other now fails a CI check. The check follows the `test-guard` pattern. ``` scripts/ci/readme-pair.sh <base-ref> merge-base diff limited to README.md, README.ja.md neither changed → ok both changed → ok one c…
12. [\[feature\] A CI gate that reports exports with no production caller (knip --production)](<https://github.com/yw0nam/YUI/issues/1758>)
   issue · 2026-10-31T13:25:22Z
   ## Work description `AGENTS.md` § Engineering principles asks the code to "delete what has no production caller", but no check enforces it: `pnpm lint` (biome) reports unused imports, not unused exports, and `scripts/ci/gates.sh` has no dead-code gate. The cost showed on "Remove…
13. [\[feature\] Remove the bed scene and every bed path](<https://github.com/yw0nam/YUI/issues/1752>)
   issue · 2026-10-31T13:03:06Z
   ## Work description Remove the bed scene: the launch scene where the character wakes on a bed, the `go_to_bed` body action, the `lying` posture, and the `wake:` line. Owner decision (2026-10-31): the furniture track does not pay back its cost, so the roadmap (#1354) and its foll…
14. [feat!: remove the bed scene, go_to_bed, the lying posture, and the wake line](<https://github.com/yw0nam/YUI/pull/1757>)
   pull_request · 2026-10-31T13:03:05Z
   ## Summary Removes the bed scene and every path it owned. The owner closed the furniture track as not planned (#1354), so the shipped stage 1 goes too. ## Breaking changes - **`body_action`**: `go_to_bed` leaves the `action` enum, and the loopback ingress `POST /avatar/command` …
15. [\[feature\] Plugin server processes orphaned by a killed app are cleaned at the next start](<https://github.com/yw0nam/YUI/issues/1698>)
   issue · 2026-10-31T12:35:46Z
   ## Work description When the app is killed without its exit hook (SIGKILL, a crash, the WebDriver session end), the MCP host's cleanup never runs. On macOS the plugin server then dies with its stdin, but a process the server itself started survives, orphaned (measured on PR #169…
16. [feat: the host kills process groups a killed app left behind at the next start](<https://github.com/yw0nam/YUI/pull/1755>)
   feature · 2026-10-31T12:35:44Z
   ## Summary When the app is killed without its exit hook, a plugin server dies with its stdin but the processes it started stay alive in its process group. The host now records each running server's process group and kills what a killed app left behind at the next start. ``` Host…
17. [docs: add the rimworld-companion skill](<https://github.com/yw0nam/YUI/pull/1482>)
   pull_request · 2026-10-31T11:38:12Z
   ## Summary Adds `skills/rimworld-companion/`, a backend-agnostic skill for an agent that watches the player's RimWorld game. It sits beside the other backend-agnostic skills in `skills/` (moved there from `integrations/skills/` when rebased onto main at 0d55551a). - `SKILL.md`: …
18. [\[feature\] Bring the README, guide and hero up to date for v0.5.0](<https://github.com/yw0nam/YUI/issues/1630>)
   issue · 2026-10-31T11:17:34Z
   ## Work description `main` is 287 commits past v0.4.0 and already declares 0.5.0 (`package.json:4`, `src-tauri/tauri.conf.json:4`, `src-tauri/Cargo.toml:3`, #1525). The README, README.ja.md, the docs site and the hero recording still describe the v0.4.0 product. This issue bring…
19. [\[feature\] Time decay of the relation value: decide after use](<https://github.com/yw0nam/YUI/issues/1540>)
   issue · 2026-10-31T11:17:32Z
   ## Work description Decide and, if wanted, add time decay to the relation value: a daily step toward neutral that stops at a band, the Stardew pattern (−2/day, stops at a band) and the Sims 4 pattern (decay only without contact, inside a middle range). #1509 shipped the store wi…
20. [\[spike\] Two VRMs in one pet window: frame budget and the borrowed character's handoff for a shared-prop scene](<https://github.com/yw0nam/YUI/issues/1539>)
   issue · 2026-10-31T11:17:29Z
   ## Uncertainty / question Can one pet window render two VRMs at an acceptable frame rate and memory cost, and what state must move when a window borrows the other character for a shared-prop scene (chair: both sit, one beckons, one declines)? #1509 chose this over a third "chair…
21. [\[bug\] The bed scene parks the same stored window size to different widths across launches (851 vs 570)](<https://github.com/yw0nam/YUI/issues/1531>)
   issue · 2026-10-31T11:17:27Z
   ## Symptoms With the same stored window size, the width the bed scene parks the window to differs between launches: 851 logical on one launch, 570 on the next. ## Steps to reproduce 1. Build the verify bundle at fade996c, bed scene on (default), store `yui.window.main = {"x":300…
22. [\[feature\] Factorio co-play P1: the body (parent)](<https://github.com/yw0nam/YUI/issues/1490>)
   issue · 2026-10-31T11:12:00Z
   ## Work description Parent issue for P1 of the Factorio co-play feature: the **body**. P0 (#1483, #1484, #1485) ships observation, the `/coop-rpc` transport, the Python Mod `Mods/factorio` with its read and talk tools, and the client's `live` delivery class. P1 gives the game mo…
23. [\[feature\] Factorio P1: owner checks on a GUI-hosted game](<https://github.com/yw0nam/YUI/issues/1499>)
   issue · 2026-10-31T11:11:57Z
   Part of #1490 ## Work description Facts P0 could not measure on the headless server because they need a real player in a GUI-hosted game. The owner runs the game once with the P0 mod from `main` and a throwaway save; the agent drives the checks over RCON and records every result…
24. [\[feature\] Factorio MCP server: per-kind doorbell cooldown, decided from measured wake rates](<https://github.com/yw0nam/YUI/issues/1500>)
   issue · 2026-10-31T11:11:55Z
   ## Work description Per-kind cooldown for the Factorio Mod's doorbell: a wake kind that fired within the last N seconds does not post another doorbell (the events stay cached and the cumulative range still covers them). Candidates: `attack_started`, `attack_ended`, `body_damaged…
25. [\[spike\] Isolated per-OS sandbox for agent-driven UI and OS-behaviour verification](<https://github.com/yw0nam/YUI/issues/1475>)
   issue · 2026-10-31T11:11:53Z
   ## Uncertainty / question Can an AI agent verify YUI's UI and OS-level behaviour (mouse, keyboard, app-to-app interaction such as perching on another app's window) in a sandbox that never touches the owner's desktop, per platform (macOS, Windows)? What does each sandbox cover, a…
26. [\[feature\] Let the user choose the pronoun the client uses for the character in client_context](<https://github.com/yw0nam/YUI/issues/1464>)
   issue · 2026-10-31T11:11:51Z
   ## Work description The `client_context` block and the contract (`docs/reference/client-context.md`) refer to the character in the third person. The lines the client emits use the gender-neutral "the character"; the contract's prose uses "she". A user who runs a male or non-bina…
27. [\[feature\] Pick the sleeping character up by a drag, and shake her out of bed](<https://github.com/yw0nam/YUI/issues/1401>)
   issue · 2026-10-31T11:11:49Z
   ## Work description Two gestures on the character while she is on the bed. This takes up the item "Shaking her out of bed" that #1354 deferred, and adds the pick-up. Direction set by the maintainer (2026-10-12): 1. **Grabbing her and dragging picks her up**, as it does when she …
28. [\[feature\] Hold the backend's speech while the character sleeps, and tell the backend she must be got up first](<https://github.com/yw0nam/YUI/issues/1391>)
   issue · 2026-10-31T11:11:46Z
   ## Work description While the character sleeps on the bed, the client holds the backend's speech, and tells the backend that she is asleep and has to be got up first. The backend decides whether to wake her and speak, or to stay silent. Today nothing holds a reply while she slee…
29. [\[feature\] An urgent backend reply wakes the sleeping character with an alarm and a hurried wake](<https://github.com/yw0nam/YUI/issues/1386>)
   issue · 2026-10-31T11:11:44Z
   ## Work description When the backend has something urgent to say while the character sleeps, an alarm goes off beside her and she gets up in a hurry, then speaks. Today a sleeping character wakes three ways: the user clicks her or sends a message, the wake timer runs out, or the…
30. [\[feature\] Roadmap: furniture and a daily life on the desktop](<https://github.com/yw0nam/YUI/issues/1354>)
   issue · 2026-10-31T11:11:42Z
   ## Work description Roadmap for making "the character lives on the desktop" visible in the product. Today the character appears from nowhere at launch, vanishes at quit, looks the same at every hour, and owns nothing on the desktop. She can walk, climb, fall and sit on window to…
