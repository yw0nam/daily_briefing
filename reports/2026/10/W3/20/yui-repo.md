---
source: "yui-repo"
date: "2026-10-20"
generated_at: "2026-10-20T08:00:11+09:00"
summary: "YUI repository: 6 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-19T23:00:11Z"}
---

# YUI repository: 6 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [fix: build the game mod's map id from the surface seed](<https://github.com/yw0nam/YUI/pull/1488>)
   pull_request · 2026-10-19T15:06:58Z
   ## Summary `map_id` is now `<surface seed>-<init tick>`, built once at `on_init`. Before, it drew one number from `game.create_random_generator(seed + tick)`; on Factorio 2.0.77 that generator's first draw is the same for every seed, so every fresh map got the id `0-22719105`. A…
2. [\[feature\] Factorio game mod P0: events, status, read ops, /coop-rpc, probe mod](<https://github.com/yw0nam/YUI/issues/1484>)
   issue · 2026-10-19T14:41:50Z
   ## Work description P0 of the Factorio co-play game mod (Lua, Factorio 2.0, working name `coop-agent`, no YUI branding), in-tree at `Mods/factorio/game-mod/`. P0 ships observation and the RPC transport, plus a dev-only probe mod that measures the facts P1 depends on. No body, no…
3. [feat: Factorio co-play game mod P0 with RCON RPC, event ring and probe mod](<https://github.com/yw0nam/YUI/pull/1487>)
   feature · 2026-10-19T14:41:48Z
   ## Summary The Factorio co-play game mod `coop-agent` (Factorio 2.0.77, Lua 5.2), P0: observation and the RPC transport, in-tree at `Mods/factorio/game-mod/`. It carries no YUI name; the Python Mod (#1485) is its only client. - **RPC.** One console command `/coop-rpc <json>` ans…
4. [\[feature\] Signals ingress: live delivery class that skips the proactive pacer and has its own cap](<https://github.com/yw0nam/YUI/issues/1483>)
   issue · 2026-10-19T13:38:39Z
   ## Work description Add a third `delivery` class to the `/signals` ingress: `live`. It marks a signal from an activity the user started and is waiting on (first producer: the Factorio co-play Mod). A `live` group is not held by the proactive pacer, merges into one catch-up turn …
5. [feat: live delivery class for the signals ingress](<https://github.com/yw0nam/YUI/pull/1486>)
   feature · 2026-10-19T13:38:37Z
   ## Summary `POST /signals` accepts a third `delivery` class, `live`, for an activity the user started and is waiting on. The first producer is the Factorio co-play Mod (#1485). - `signals-source` parses each inbox arrival once and routes it by delivery class to one of two `Buffe…
6. [\[spike\] Co-playing agent: which games expose an action interface, and what shape the Mod takes](<https://github.com/yw0nam/YUI/issues/1463>)
   issue · 2026-10-19T12:40:26Z
   ## Uncertainty / question The end goal is for the backend agent to play the game together with the user. Which of the target games expose an action interface an agent can use, and what shape should the YUI side take? What the web search found so far (not run or verified locally)…
