---
source: "yui-repo"
date: "2026-10-24"
generated_at: "2026-10-24T08:00:11+09:00"
summary: "YUI repository: 20 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-23T23:00:11Z"}
---

# YUI repository: 20 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] Card import and export: Tavern V2/V3 JSON and PNG in, V2 JSON out, PNG thumbnail on the preset](<https://github.com/yw0nam/YUI/issues/1565>)
   issue · 2026-10-23T15:02:48Z
   ## Work description Import a Tavern character card into a new preset and export a preset's card. Builds on the card storage of #1564. Decision record: #1563. Owner decisions: - **Import formats.** JSON (`chara_card_v2` and `chara_card_v3`) and PNG (the `chara` tEXt chunk holding…
2. [feat: card import and export: Tavern V2/V3 JSON and PNG in, V2 JSON out, a PNG thumbnail on the preset, and one greeting at the imported preset's first boot](<https://github.com/yw0nam/YUI/pull/1570>)
   feature · 2026-10-23T15:02:46Z
   ## Summary A Tavern card imports as a new preset, and a preset's card exports as V2 JSON. The two OS dialogs open in Rust, so the webview never names a file path. ``` Talk tab · Card section (below the Send card body) [Import card…] [Export card] JSON or PNG card in · V2 JSON ou…
3. [chore: CI fails when a bare class selector is declared in two stylesheets](<https://github.com/yw0nam/YUI/pull/1569>)
   pull_request · 2026-10-23T14:37:27Z
   ## Summary `pnpm css:check` (`scripts/ci/css-selectors.mjs`) fails when the same bare class selector (`.yui-x {`) is declared in two stylesheets under `src/`, and runs in the `web` CI job after `map:check`. Why: on #1568 the new `.yui-source` block inherited `display: none` from…
4. [\[feature\] Signal source lines on the speech bubble, and History records every signal](<https://github.com/yw0nam/YUI/issues/1552>)
   issue · 2026-10-23T14:17:15Z
   Part of #1549 ## Work description On a background turn that carries signals, the speech bubble shows where each signal came from, and History records every signal, whether the backend spoke or stayed silent. Mock: https://claude.ai/artifact/WeGX6hhRtQaifn6aqqzxLt (private to the…
5. [feat: signal source lines on the speech bubble, and History records every signal, spoken or silent](<https://github.com/yw0nam/YUI/pull/1568>)
   feature · 2026-10-23T14:17:13Z
   ## Summary A turn that carries signal groups now says where they came from, and History keeps every signal, spoken or silent. ``` POST /signals ──► inbox ──► turn(trigger.signals) ──► backend │ │ reply / [SILENT] ├─ recordSentTurn ─────┤─► transcript (assistant row, turn_id; non…
6. [\[feature\] Card per preset: Tavern V2 persona text, language defaults, send switch, editor, greeting replay](<https://github.com/yw0nam/YUI/issues/1564>)
   issue · 2026-10-23T13:12:57Z
   ## Work description Each preset carries a **Card**: its persona text in Tavern Card V2 shape. On the request transports the client sends the card as the first system message, ahead of `chat_instructions`. Push presets have no card section. Decision record: #1563. Owner decisions…
7. [feat: a card per preset: Tavern V2 persona text as the system message, language defaults, a send switch, the Talk-tab editor, and a greeting after Start fresh](<https://github.com/yw0nam/YUI/pull/1567>)
   feature · 2026-10-23T13:12:56Z
   ## Summary Each preset carries a **Card**: its persona text in Tavern Card V2 shape. On the request transports the client sends the assembled card as the first system message (Chat Completions) or `instructions` (Responses), followed by `chat_instructions`; push presets send non…
8. [\[feature\] Docs: persona text moves to the client, two-tier backend recommendation, OpenAI-only quickstart](<https://github.com/yw0nam/YUI/issues/1563>)
   issue · 2026-10-23T11:54:46Z
   ## Work description Product decision: the persona **text** (who the character is, how she talks) is client-side configuration that the client sends as the system message on the request transports. Judgment stays in the backend: how to act the text, and whether to speak at all. `…
9. [docs: persona text is client configuration; backends recommended by capability; one-key OpenAI quickstart](<https://github.com/yw0nam/YUI/pull/1566>)
   pull_request · 2026-10-23T11:54:45Z
   ## Summary Product decision recorded in the docs ahead of the code (#1564, #1565): the persona text (who the character is, how she talks) is client configuration, sent as the first system message on Chat Completions and as `instructions` on Responses, never on push. Judgment sta…
10. [\[feature\] yui-notify plugin: Claude Code and Codex hooks post done and needs-input signals, with a setup skill](<https://github.com/yw0nam/YUI/issues/1551>)
   issue · 2026-10-23T11:53:06Z
   Part of #1549 ## Work description A plugin that Claude Code and Codex both install, whose hooks post `agent.done` and `agent.needs_input` signals to YUI, and whose `setup` skill configures it by conversation. It assumes nothing about the user's machines: every value comes from s…
11. [feat: yui-notify plugin: Claude Code and Codex hooks post done and needs-input signals, with a setup skill](<https://github.com/yw0nam/YUI/pull/1562>)
   feature · 2026-10-23T11:53:04Z
   ## Summary A plugin that Claude Code and Codex both install. Its hooks post `agent.done` and `agent.needs_input` signals to `POST /signals`, and its user-invoked `setup` skill configures it by conversation. ``` .claude-plugin/marketplace.json marketplace "yui" → ./integrations/y…
12. [\[spike\] Batched signals after a missed deadline and after a reload](<https://github.com/yw0nam/YUI/issues/1556>)
   issue · 2026-10-23T06:40:32Z
   ## Uncertainty / question Two buffer behaviours in `src/dispatcher/sources/inbox/signals-source.ts` lose or hold signals. Decide whether to change each, and how. 1. When the batched timer fires and the group cannot go out (user away, pipeline busy, signals off), the timer is not…
13. [\[spike\] Backend pulls signal and session detail on demand instead of receiving it](<https://github.com/yw0nam/YUI/issues/1555>)
   issue · 2026-10-23T06:40:29Z
   ## Uncertainty / question Should the backend receive only a short signal and pull the details when it needs them? Two cases: 1. A signal store the backend can query through a client tool (items, history), so the prompt carries a short line and not the full item. 2. For coding-ag…
14. [\[feature\] Signals contract: urgent tier, replace by event_id, 16 KiB item cap, envelope label, deprecate immediate and /agent-event](<https://github.com/yw0nam/YUI/issues/1550>)
   issue · 2026-10-23T06:35:07Z
   Part of #1549 ## Work description The `/signals` contract change that every other child builds on: the `urgent` tier, replacement by `event_id`, the item size cap, the envelope `label`, two deprecations, and the docs and product principle that go with them. ## Acceptance criteri…
15. [feat: signals contract: urgent delivery class, replace by event_id, 16 KiB item cap, envelope label, and deprecate immediate and /agent-event](<https://github.com/yw0nam/YUI/pull/1559>)
   feature · 2026-10-23T06:35:05Z
   ## Summary The `/signals` contract that the other #1549 children build on. ``` producer ──POST /signals──► shell/agent-ingress (Rust) └ any item > 16 KiB → 400, whole request ──signals-inbox──► dispatcher/sources/inbox/signals-source (TS) ├ validEnvelope: delivery urgent | batch…
16. [\[feature\] The relation line scales: the matrix goes, chips sort by strength and fold closed presets, and an empty line replaces the hidden one](<https://github.com/yw0nam/YUI/issues/1547>)
   issue · 2026-10-23T02:41:07Z
   ## Work description The relations matrix under the preset row does not scale: its table is N rows by N+1 columns in a 25rem panel, so from six presets the cells squeeze and names truncate, and most cells are dashes. Every shipped product shows relationships as an ego view instea…
17. [feat: the relation line scales: the matrix goes, chips sort by strength and fold closed presets, and an empty line replaces the hidden one](<https://github.com/yw0nam/YUI/pull/1548>)
   feature · 2026-10-23T02:41:06Z
   ## Summary The relations matrix under the preset row goes, and the relation line becomes the one relation view: its chips sort by strength after "you", rated targets whose preset window is closed fold into one trailing `+N` chip, and an unrated preset shows "No one rated yet" in…
18. [chore: the relay kill test drops its racing clock check, and CI rejects a PR body with an AI attribution line](<https://github.com/yw0nam/YUI/pull/1544>)
   pull_request · 2026-10-23T00:53:55Z
   ## Summary Two retro items from the #1543 session. - `src-tauri/src/browser/relay.rs`: the test `run_kills_a_script_that_never_yields_to_its_deadline` asserted `started.elapsed() < kill_after + 1 s` after the `tokio::time::timeout` with the same bound had already resolved, so a …
19. [\[feature\] Relation values per character: client store, rate_relation tool, ingress route, stance line, band glyph](<https://github.com/yw0nam/YUI/issues/1538>)
   issue · 2026-10-23T00:53:45Z
   ## Work description The client stores each character's stance toward the user and toward every other preset, lets the backend move it through a client tool, lets an external memory read and write it over the ingress, renders the character's own stance into `client_context`, and …
20. [feat: relation values per character: rate_relation, the relation line in client_context, GET/PUT /relations, and the relation line in the preset strip](<https://github.com/yw0nam/YUI/pull/1543>)
   feature · 2026-10-23T00:53:44Z
   ## Summary A character keeps a one-axis relation toward the user and toward each other open character. The backend moves it through a `rate_relation` tool, the next turn's `client_context` carries it as a `relation:` line, an external engine can read and replace it over the ingr…
