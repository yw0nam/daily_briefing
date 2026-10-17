---
source: "yui-repo"
date: "2026-10-18"
generated_at: "2026-10-18T08:00:09+09:00"
summary: "YUI repository: 10 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-17T23:00:09Z"}
---

# YUI repository: 10 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [\[feature\] Opt-in embedded WebDriver (verify feature) for the verify bundle](<https://github.com/yw0nam/YUI/issues/1480>)
   issue · 2026-10-17T06:18:13Z
   ## Work description The spike in #1477 showed that Tauri's embedded WebDriver provider (`tauri-plugin-wdio-webdriver` + `@wdio/tauri-service`) attaches to the verify bundle on macOS and gives JavaScript evaluation, DOM reads, a `localStorage` seed with reload, and pointer-event …
2. [feat: opt-in verify feature with the embedded WebDriver plugin](<https://github.com/yw0nam/YUI/pull/1481>)
   feature · 2026-10-17T06:18:12Z
   ## Summary Ships the embedded WebDriver provider measured in #1477 as an opt-in Cargo feature. - **`verify` feature.** `src-tauri/Cargo.toml` declares `tauri-plugin-wdio-webdriver = { version = "1.5.0", optional = true }` and `verify = ["dep:tauri-plugin-wdio-webdriver"]`. It is…
3. [\[spike\] Does Tauri's embedded WebDriver provider reach the YUI verify bundle on macOS?](<https://github.com/yw0nam/YUI/issues/1477>)
   issue · 2026-10-17T05:53:28Z
   ## Uncertainty / question Tauri's WebDriver guide (https://v2.tauri.app/develop/tests/webdriver/) states that WebdriverIO with `@wdio/tauri-service` and its default `embedded` driver provider works on macOS, through a Tauri plugin added to the app. Stock `tauri-driver` still has…
4. [\[feature\] Debug-build settings seed for the verify bundle (YUI_SETTINGS_SEED)](<https://github.com/yw0nam/YUI/issues/1478>)
   issue · 2026-10-17T05:53:26Z
   ## Work description A verification run of the desktop app needs the agent-ingress listener enabled and the chat endpoint pointed at a mock server before the first turn fires. Both live in `localStorage` (`yui.agentNotify`, `yui.endpoints`), and the only way to set them today is …
5. [\[feature\] Log lines for the states agents cannot see today](<https://github.com/yw0nam/YUI/issues/1476>)
   issue · 2026-10-17T05:52:10Z
   ## Work description Agents verify runtime behaviour from `logs/*.log` (`pnpm tauri:dev`, the verify bundle). Six states happen today without any log line, so an agent falls back to screenshots or temporary code to see them. This issue adds one log line per state, following `docs…
6. [feat: log the states agents could not see](<https://github.com/yw0nam/YUI/pull/1479>)
   feature · 2026-10-17T05:52:09Z
   ## Summary Adds one log line for each of the seven states the issue lists, so an agent reading `logs/*.log` can see them without screenshots or temporary code. Each line follows `docs/reference/logging.md`: a snake_case event name and named fields, with no chat text, tool result…
7. [test: keep the config invariants and drop the blocks that mirrored tunable values](<https://github.com/yw0nam/YUI/pull/1474>)
   pull_request · 2026-10-17T03:11:28Z
   ## Summary `src/config/configs.test.ts` keeps the invariants the shipped configs under `configs/` must hold and drops the blocks that restated a tunable's current value. The file goes from 51 blocks (54 cases) to 16 blocks (54 cases); the mutations listed below each made their b…
8. [docs: state what a test must prove and when a test is not written](<https://github.com/yw0nam/YUI/pull/1472>)
   pull_request · 2026-10-17T02:47:33Z
   ## Summary `docs/agent-guide/testing.md` opens with what a test is for, so a contributor can tell a test that earns its place from one that adds volume. The existing rules say how to write a test (public entry, literal expectations, red before green); none said what a failing te…
9. [test: fix two assertions that could not fail](<https://github.com/yw0nam/YUI/pull/1473>)
   pull_request · 2026-10-17T02:46:38Z
   ## Summary Two test blocks found by a full read of the suite do not detect the regressions their titles name. - `src/dispatcher/backend/backend-caller.context.test.ts` "renders no previous line when the slot is empty" asserted the absence of `previous:`; the rendered line begins…
10. [chore: align agent docs and config with the repo after the audit](<https://github.com/yw0nam/YUI/pull/1471>)
   pull_request · 2026-10-17T02:26:48Z
   ## Summary Follow-up to a repository audit (four read-only scans: tooling and CI, agent-doc accuracy, the architecture map, and a set of outside design references). Everything here is docs, config, or the map viewer; no `src/` or `src-tauri/src/` file changes. **Docs that had dr…
