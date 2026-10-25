---
source: "yui-repo"
date: "2026-10-26"
generated_at: "2026-10-26T08:00:12+09:00"
summary: "YUI repository: 7 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-25T23:00:12Z"}
---

# YUI repository: 7 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [chore: snake_case log event names are checked, the smoke test declares per-client tools, .any-subagent is ignored](<https://github.com/yw0nam/YUI/pull/1587>)
   pull_request · 2026-10-25T12:46:14Z
   ## Summary Retro of the #1546/#1583 session, the mechanical part. - `scripts/ci/logger-namespace.mjs` also refuses a log event name that is not `snake_case` (dots between segments allowed: `backend_call.unexpected_error`). The eight names with spaces (`push rejected`, `signal dr…
2. [\[feature\] Unified chat window with @ routing across open characters](<https://github.com/yw0nam/YUI/issues/1583>)
   issue · 2026-10-25T12:31:37Z
   ## Work description Today each preset has its own message window with its own composer, so talking to a second character means switching windows. A unified chat window shows every open character's conversation in one time-ordered view and routes the user's input with `@`, the wa…
3. [feat: unified chat window routes the user's messages to the open characters](<https://github.com/yw0nam/YUI/pull/1585>)
   feature · 2026-10-25T12:31:36Z
   ## Summary One window for every open character: the unified chat window lists every open preset's current-session transcript in one time order and routes the user's messages to one preset, to the last speaker, or to every open preset one after another. ``` settings (Talk tab) ma…
4. [\[feature\] A character addresses another open character through a tool and that character receives a turn](<https://github.com/yw0nam/YUI/issues/1546>)
   issue · 2026-10-25T11:43:08Z
   ## Work description Today a character only overhears other open characters: the next turn's `client_context` carries their recent transcript lines (#1536, #1542), and nothing opens a turn for a character that was spoken to. A character should be able to address another open char…
5. [feat: address_character routes a reply to another open character, with a chain cap](<https://github.com/yw0nam/YUI/pull/1584>)
   feature · 2026-10-25T11:43:07Z
   ## Summary A character can speak to another open character, and that character receives a turn whose trigger says so. The client routes; the backend judges. ``` pet window A (perlica) pet window B (natsume) backend calls address_character {to: "natsume"} ──► tool records the tur…
6. [\[feature\] Edit relation values by hand in the settings window](<https://github.com/yw0nam/YUI/issues/1541>)
   issue · 2026-10-25T09:37:42Z
   ## Work description Let the user edit a character's relation values by hand in the settings window: per target, the band and the value, with the change written to the store as a log entry `why: "set by the user"`. #1509 chose the ingress `GET/PUT` route first (Q11 (a)) so an ext…
7. [feat: edit relation values by hand in the Character tab, with a Relations switch](<https://github.com/yw0nam/YUI/pull/1582>)
   feature · 2026-10-25T09:37:41Z
   ## Summary The Character tab gains a Relations section: one slider row per target (the user and every other preset), rated rows first, unrated rows after a stronger hairline. Dragging previews the glyph, band word and number; releasing writes the value. A device-wide Relations s…
