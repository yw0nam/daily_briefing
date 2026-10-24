---
source: "yui-repo"
date: "2026-10-25"
generated_at: "2026-10-25T08:00:11+09:00"
summary: "YUI repository: 17 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-24T23:00:11Z"}
---

# YUI repository: 17 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[chore\] Move the two-phase import flow out of user-asset-list.ts into its own module](<https://github.com/yw0nam/YUI/issues/1575>)
   issue · 2026-10-24T13:41:23Z
   ## Work description `src/ui/quick-controls/sections/user-asset-list.ts` is a 530-line `create*` closure that holds the list's rename FSM, removal, swap orchestration, keyboard navigation and the two-phase import flow (`pendingImport`, `picking`, `disposed`, `startPendingImport`,…
2. [refactor: move the two-phase import flow out of user-asset-list.ts](<https://github.com/yw0nam/YUI/pull/1581>)
   pull_request · 2026-10-24T13:41:22Z
   ## Summary A split, no behaviour change. The two-phase import flow (a staged voice import awaiting a name) leaves the `createUserAssetList` closure for its own module: ``` src/ui/quick-controls/sections/ user-asset-list.ts 531 → 420 lines rename FSM · removal · swap · keyboard n…
3. [\[feature\] Answer in place: replace flows that send the user to the settings window](<https://github.com/yw0nam/YUI/issues/1557>)
   issue · 2026-10-24T13:41:20Z
   Part of #1549 ## Work description Apply PRODUCT.md principle 6, "Answer in place" (added by the contract child): find every flow in which a surface other than the settings window sends the user into the settings window to read state or finish its job, and replace each with an an…
4. [feat: the delegation chip names the lost connection's cause in place](<https://github.com/yw0nam/YUI/pull/1580>)
   feature · 2026-10-24T13:41:18Z
   ## Summary PRODUCT.md principle 6, "Answer in place": no surface sends the user into the settings window to read state. This PR applies it to the one flow that did, and lists every other call site with its resolution. ``` delegation chip, socket not ready before: label "Connecti…
5. [\[feature\] Catch-up markers stop saying "while I was away" for a busy or pacer catch-up](<https://github.com/yw0nam/YUI/issues/1561>)
   issue · 2026-10-24T13:13:45Z
   Part of #1549. Found by the #1556 spike. ## Work description The two catch-up markers say "while I was away" for every catch-up. A catch-up also fires on the busy-to-idle edge and when the pacer stops holding (`src/dispatcher/sources/inbox/buffered-inbox-source.ts`, `src/dispatc…
6. [feat: catch-up markers stop saying "while I was away"](<https://github.com/yw0nam/YUI/pull/1579>)
   feature · 2026-10-24T13:13:44Z
   ## Summary Two background markers change wording, nothing else: ``` backgroundMarker("signals.catchup") "(signals piled up while I was away)" → "(signals piled up for you)" backgroundMarker("signals.urgent_catchup") "(urgent things piled up while I was away)" → "(urgent things p…
7. [\[feature\] STT language setting for OpenAI-compatible Whisper](<https://github.com/yw0nam/YUI/issues/1577>)
   issue · 2026-10-24T12:43:31Z
   ## Work description The STT request sends only `file` and `model`. Whisper auto-detects the spoken language per segment, and a short or accented utterance can come back in the wrong language. OpenAI's `/audio/transcriptions` takes an optional `language` (ISO-639-1, e.g. `en`); t…
8. [feat: stt_language sends the Whisper language, with Auto/en/ja suggestions](<https://github.com/yw0nam/YUI/pull/1578>)
   feature · 2026-10-24T12:43:29Z
   ## Summary The STT request now carries Whisper's `language` field when `stt_language` is set. ``` configs/endpoints.json / Connection tab "STT language" (stt_language) → mergeEndpoints → EndpointsConfig.stt_language → stt-vad onSpeechEnd: form.append("language", …) unless unset …
9. [\[feature\] VRM, stage image, and voice imports open their file dialog in Rust, like the card import; the webview passes no path](<https://github.com/yw0nam/YUI/issues/1571>)
   issue · 2026-10-24T07:24:02Z
   ## Work description Three Tauri commands take a file path the webview chose through the JS dialog plugin and then read that path: `import_vrm_file(src_path: FilePath, …)` in `src-tauri/src/vrm_import.rs`, `import_stage_image(src_path: FilePath)` in `src-tauri/src/stage_image.rs`…
10. [feat: VRM, stage image, and voice imports open their file dialog in Rust; the webview passes no path](<https://github.com/yw0nam/YUI/pull/1576>)
   feature · 2026-10-24T07:24:01Z
   ## Summary The VRM, stage image and voice imports open their OS file picker inside the Rust command, as the card import does (#1570); the webview passes no path, `@tauri-apps/plugin-dialog` leaves the JS side and `dialog:allow-open` leaves both capability files, and `scripts/ci/…
11. [\[bug\] Two paced catch-ups on the same return tick: the second is dropped as global_gap and its groups are lost](<https://github.com/yw0nam/YUI/issues/1558>)
   issue · 2026-10-24T07:23:39Z
   ## Symptoms When two paced buffered-inbox sources flush a catch-up on the same return-from-away tick, only the first catch-up reaches the backend. The dispatcher drops the second one as `global_gap`, and its source has already cleared its buffer, so those groups are lost. Measur…
12. [\[bug\] A signal group drained into a turn is lost when the turn is dropped](<https://github.com/yw0nam/YUI/issues/1560>)
   issue · 2026-10-24T07:23:38Z
   Part of #1549. Found by the #1556 spike. ## Symptoms A signal group that the client drains into a turn is lost when that turn does not reach the backend. The ingress already answered 200, so the producer does not send the group again. No log line records the loss. ## Steps to re…
13. [fix: a dropped turn's signal groups go back to the front of their buffers](<https://github.com/yw0nam/YUI/pull/1574>)
   pull_request · 2026-10-24T07:23:37Z
   ## Summary A signal group that rode on a turn the client dropped, or on a push the bus refused, goes back to the front of its buffer; the next edge or drain delivers it. Before, the ingress had answered 200, the source had cleared its buffer, and nothing returned the group (#156…
14. [\[feature\] Signal chips beside the avatar: card on tap, dismiss, expand, fold](<https://github.com/yw0nam/YUI/issues/1553>)
   issue · 2026-10-24T07:23:20Z
   Part of #1549 ## Work description A signal chip beside the avatar for each signal group, in the same pill family as the delegation chip, with a card on tap and × to dismiss. Mock: https://claude.ai/artifact/WeGX6hhRtQaifn6aqqzxLt (private to the owner). ## Acceptance criteria - …
15. [feat: signal chips beside the avatar with a details sheet on tap, dismiss, expand and a shared fold](<https://github.com/yw0nam/YUI/pull/1573>)
   feature · 2026-10-24T07:23:18Z
   ## Summary One pill per signal group beside the avatar, above the delegation chip, in a new chip column of the overlay; a details sheet on tap; × dismisses; "+N" expands in place; a held press folds every chip through the fold store the delegation chip already keeps. ``` shell/a…
16. [\[chore\] Docs drift: ingress, signals, hooks and client_context docs against the code](<https://github.com/yw0nam/YUI/issues/1554>)
   issue · 2026-10-24T07:22:23Z
   Part of #1549 ## Work description After the other children merge, compare every doc about the ingress, signals, hooks and `client_context` with the code, and fix each place where they differ. ## Acceptance criteria - [ ] Scope read in full: `docs/reference/signals-ingress.md`, `…
17. [docs: ingress, signals, hooks and client_context docs match the code](<https://github.com/yw0nam/YUI/pull/1572>)
   pull_request · 2026-10-24T07:22:21Z
   ## Summary Every doc about the ingress, signals, hooks and `client_context` was compared with the code at `de6b9aae`; each difference is fixed in the doc, and the code changes only where the doc stated the intended behaviour (one comment, one label). 13 files, 28 insertions. | #…
