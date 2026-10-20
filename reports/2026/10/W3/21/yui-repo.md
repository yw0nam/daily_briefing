---
source: "yui-repo"
date: "2026-10-21"
generated_at: "2026-10-21T08:00:12+09:00"
summary: "YUI repository: 24 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-20T23:00:11Z"}
---

# YUI repository: 24 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[spike\] Several pet windows at once, one per preset: owner-window design for hotkey, tray, microphone, signals and avatar RPC](<https://github.com/yw0nam/YUI/issues/1508>)
   issue · 2026-10-20T08:28:41Z
   ## Uncertainty / question Can the client run **two or more pet windows at once, one per preset** (one character per window), on top of the preset feature from #1503? Presets already namespace every per-character key, so the open question is the window side: which behaviours assu…
2. [\[feature\] Factorio P1: companion skill for the backend agent](<https://github.com/yw0nam/YUI/issues/1497>)
   issue · 2026-10-20T08:05:49Z
   Part of #1490 ## Work description Companion skill `integrations/skills/factorio-companion/SKILL.md` for any backend agent that speaks the YUI contract (backend-agnostic: no agent name, no install route of one agent). Content, in STE (one sentence per fact): 1. **Setup for the ow…
3. [docs: align the Factorio companion skill with the P1 tools and name the skills toolset](<https://github.com/yw0nam/YUI/pull/1515>)
   pull_request · 2026-10-20T08:05:48Z
   ## Summary Final pass on `integrations/skills/factorio-companion/SKILL.md`: the skill now matches the shipped P1 contract word for word (13 tools with their argument shapes, five job kinds with defaults, 13 reason codes, every event kind and the default wake set, idle and threat…
4. [\[feature\] Factorio P1: threat safety and retreat](<https://github.com/yw0nam/YUI/issues/1495>)
   issue · 2026-10-20T07:25:16Z
   Part of #1490 ## Work description Mechanical threat safety for the body in `coop-agent`: new module `scripts/threat.lua`, hooked into the walker and the job runner of child 2. Safe radius: mod setting `safe radius`, default 48 tiles. Enemy means a military entity of a force that…
5. [feat: Factorio game mod threat safety with target, route and body checks and a retreat to the host](<https://github.com/yw0nam/YUI/pull/1514>)
   feature · 2026-10-20T07:25:14Z
   ## Summary The `coop-agent` game mod gains mechanical threat safety: the body never walks into enemies, and it retreats to the host when enemies come to it. Waking is not acting: the backend hears `body_threat` and `body_damaged` (opt-in wake kinds), and the body never attacks. …
6. [\[feature\] Factorio P1: Mods/factorio job, idle and stop tools](<https://github.com/yw0nam/YUI/issues/1496>)
   issue · 2026-10-20T07:01:35Z
   Part of #1490 ## Work description P1 tools in the Python Mod `Mods/factorio` (FastMCP, port 9003), one tool per new game op, in a new module `factorio/tools/body.py` registered through the existing `ToolDeps`: | Tool | Game op | Notes | |---|---|---| | `factorio_jobs()` | `jobs`…
7. [feat: Factorio Mod job, idle and stop tools with the P1 wake set](<https://github.com/yw0nam/YUI/pull/1513>)
   feature · 2026-10-20T07:01:33Z
   ## Summary The Python Mod `Mods/factorio` gains the P1 body tools and the P1 wake set, so a backend agent can drive the body through the same MCP server that already reads the game. - **Tools** (new module `factorio/tools/body.py`, registered through the one `ToolDeps`): `factor…
8. [\[feature\] Factorio P1: idle modes follow/stay and idle_set](<https://github.com/yw0nam/YUI/issues/1492>)
   issue · 2026-10-20T06:28:29Z
   Part of #1490 ## Work description Idle behaviour of the body in `coop-agent`: new module `scripts/idle.lua` and the op `scripts/ops/idle_set.lua`. - **Modes.** `follow` (default from the mod setting `idle start`): keep 10 to 15 tiles from the host with repeated short walker step…
9. [feat: Factorio game mod idle modes follow and stay with idle_set and the follow job](<https://github.com/yw0nam/YUI/pull/1512>)
   feature · 2026-10-20T06:28:28Z
   ## Summary The `coop-agent` game mod gains idle behaviour: what the body does when the queue is empty. - **Modes.** `follow` keeps the body 10 to 15 tiles from the host with short steps through the one walker; a step is cancelled when the host comes within 10 tiles. Beyond a 64-…
10. [\[feature\] Factorio P1: deliver job (spill at the host, to_be_looted)](<https://github.com/yw0nam/YUI/issues/1494>)
   issue · 2026-10-20T05:45:37Z
   Part of #1490 ## Work description The `deliver{item, count}` job in `coop-agent`: new module `scripts/jobs/deliver.lua`. - Walk to within 3 tiles of the host. - Remove `count` of `item` from the body inventory first (`inventory.remove` returns the removed count; fewer than `coun…
11. [feat: Factorio game mod deliver job that leaves the pile at the host's feet](<https://github.com/yw0nam/YUI/pull/1511>)
   feature · 2026-10-20T05:45:35Z
   ## Summary The `coop-agent` game mod gains the `deliver{item, count}` job: the body brings `count` of `item` to the host and leaves the pile at the host's feet as looted ground items, which the host's character picks up by walking over them. - **Flow.** `no_item{item, count, hel…
12. [\[bug\] Connection tab: Broker section title and its state text overlap in a narrow settings window](<https://github.com/yw0nam/YUI/issues/1507>)
   issue · 2026-10-20T04:46:41Z
   ## Symptoms In the settings window's Connection tab, the **Broker** section title and the state text to its right ("MCP streamable-http, deprecated, removed in v0.6.0") draw on top of each other when the window is narrow. The hint also runs past the panel's right edge. ## Steps …
13. [fix: keep the Connection section title beside its state text in a narrow panel](<https://github.com/yw0nam/YUI/pull/1510>)
   pull_request · 2026-10-20T04:46:39Z
   ## Summary In a narrow settings window the Connection tab's **Broker** section title and the state text at its right ("MCP streamable-http, deprecated, removed in v0.6.0") drew over each other, and the text ran past the panel edge. `.yui-endpoints__hint` had `flex: none` with no…
14. [\[feature\] Character presets: per-preset connection, voice, history, VRM, and filler with a switch in the quick-controls panel](<https://github.com/yw0nam/YUI/issues/1503>)
   issue · 2026-10-20T04:38:03Z
   ## Work description A **preset** bundles the per-character state of the client so the user can keep several characters (for example `natsume`, `perlica`) on one machine and switch between them without restarting the app. Selecting a preset swaps the backend connection, the TTS v…
15. [feat: character presets with per-preset connection, voice, history, VRM, and filler](<https://github.com/yw0nam/YUI/pull/1506>)
   feature · 2026-10-20T04:38:02Z
   ## Summary A **preset** bundles the per-character state of the client so one machine can keep several characters and switch between them without restarting the app. The active preset decides which copy of the connection, voice-output, conversation, VRM-selection and filler keys …
16. [\[feature\] Factorio P1: mine job (native mining with timed fallback)](<https://github.com/yw0nam/YUI/issues/1493>)
   issue · 2026-10-20T04:27:53Z
   Part of #1490 ## Work description The `mine{name, count}` job in `coop-agent`: new module `scripts/jobs/mine.lua`. - **Target.** The nearest entity within 64 tiles of the body that yields `name` and is allowed: resources, trees, rocks, entities the body built, and entities the h…
17. [feat: Factorio game mod mine job with native mining and a timed fallback](<https://github.com/yw0nam/YUI/pull/1505>)
   feature · 2026-10-20T04:27:52Z
   ## Summary The `coop-agent` game mod gains the `mine{name, count, entity?}` job: the body walks to the nearest entity that yields `name`, mines it natively, and ends when it has gained `count` of that item. - **Target.** The nearest allowed entity within 64 tiles whose `mineable…
18. [\[feature\] Factorio P1: job queue, walker, walk_to and wait](<https://github.com/yw0nam/YUI/issues/1491>)
   issue · 2026-10-20T03:52:27Z
   Part of #1490 ## Work description Job queue, walker, and the first two jobs in `coop-agent`: new modules `scripts/jobs.lua` (queue and runner), `scripts/walker.lua` (the one path walker every movement uses), `scripts/ops/jobs.lua`, `scripts/ops/jobs_enqueue.lua`, `scripts/ops/jo…
19. [feat: Factorio game mod job queue, path walker, walk_to and wait](<https://github.com/yw0nam/YUI/pull/1504>)
   feature · 2026-10-20T03:52:26Z
   ## Summary The `coop-agent` game mod gains the job queue, the one path walker every movement uses, and the first two job kinds. The backend queues work through RCON; the mod runs it tick by tick behind the body's execution gate. - **Queue.** FIFO in `storage.jobs`, at most 16 qu…
20. [\[feature\] Factorio P1: body lifecycle (spawn, kit, status line, death/respawn, stop)](<https://github.com/yw0nam/YUI/issues/1498>)
   issue · 2026-10-20T02:55:57Z
   Part of #1490 ## Work description Body lifecycle in the game mod `coop-agent` (`Mods/factorio/game-mod/coop-agent/`), as a new module `scripts/body.lua` wired at the root of `control.lua`. - **Spawn.** When the mod setting `body enabled` is on, the host is connected, and no live…
21. [feat: Factorio game mod body lifecycle with stop latch, execution gate and status line](<https://github.com/yw0nam/YUI/pull/1502>)
   feature · 2026-10-20T02:55:56Z
   ## Summary The `coop-agent` game mod gains the body: one playerless `character` that the mod keeps beside the host while the mod setting `body enabled` is on. This PR is the lifecycle only (spawn, kit, color, status line, death and respawn, stop latch and execution gate); the jo…
22. [docs: add the Factorio companion skill](<https://github.com/yw0nam/YUI/pull/1501>)
   pull_request · 2026-10-20T02:35:52Z
   ## Summary Adds `integrations/skills/factorio-companion/SKILL.md`, the backend-agnostic skill a backend agent loads to play Factorio through the `factorio` Mod. It covers the owner setup steps, how a `game.wake` live signal is read and paged, every event kind and which ones wake…
23. [\[feature\] Mods/factorio P0: RCON poll, event cache, factorio_* tools, live doorbell](<https://github.com/yw0nam/YUI/issues/1485>)
   issue · 2026-10-20T00:39:09Z
   ## Work description P0 of `Mods/factorio`: a YUI Mod (uv project, FastMCP ≥ 3.4.3, HTTP on `127.0.0.1:9003` with `host_origin_protection=True`, router key `factorio`) that connects the Factorio game mod to any backend agent and to the YUI client. **RCON client.** Source RCON ove…
24. [feat: Factorio MCP Mod that polls the game mod over RCON and rings the live doorbell](<https://github.com/yw0nam/YUI/pull/1489>)
   feature · 2026-10-20T00:39:08Z
   ## Summary `Mods/factorio`, the Python MCP Mod (FastMCP, port 9003, router key `factorio`, `host_origin_protection=True`) that bridges the in-tree Factorio game mod (`Mods/factorio/game-mod/`) to the backend agent and to the YUI client. It runs host-native beside the game and re…
