---
source: "yui-repo"
date: "2026-10-16"
generated_at: "2026-10-16T08:00:09+09:00"
summary: "YUI repository: 22 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo."
sources:
  - {name: "github.com/yw0nam/YUI", status: "ok", last_ok: "2026-10-15T23:00:09Z"}
---

# YUI repository: 22 updates in the last 24 hours, including closed issues, merged pull requests, features, and review requests for Youngwoo.

1. [test: type voice mocks from their modules and write mock defaults in one vi.fn form](<https://github.com/yw0nam/YUI/pull/1468>)
   pull_request · 2026-10-15T11:54:35Z
   ## Summary Cleanups to the mock defaults that #1467 moved to `vi.fn(impl)`, and the test rule that names the typed form. No default value, assertion, or test name changes. 1. `listVoices`, `upsertVoice`, `listFishVoices`, `copyVoiceFile` and `removeOrphanImport` take their type …
2. [fix: reset mocks between tests so an unused queued value cannot leak](<https://github.com/yw0nam/YUI/pull/1467>)
   pull_request · 2026-10-15T11:30:36Z
   ## Summary `clearMocks` (#1460) clears calls and results before each test and keeps unused `*Once` queues, so a value a test queues with `mockReturnValueOnce` / `mockResolvedValueOnce` / `mockImplementationOnce` and does not consume is returned to the next test that calls the mo…
3. [test: drop mock clears that clearMocks covers and settle a travel-frame test's wiring](<https://github.com/yw0nam/YUI/pull/1466>)
   pull_request · 2026-10-15T08:47:11Z
   ## Summary Follow-up to #1460, which set `clearMocks: true`. 1. Removes 47 mock clears (`x.mockClear()`, `vi.mocked(x).mockClear()`, `vi.clearAllMocks()`) across 16 test files, counted with `git diff main...HEAD | grep -cE '^-.*(mockClear\(\)|clearAllMocks\(\))'`. Each opened a …
4. [fix: client_context lines name the actor and separate states from events](<https://github.com/yw0nam/YUI/pull/1465>)
   pull_request · 2026-10-15T08:17:44Z
   ## Summary The backend model reads the `<client_context>` block as prose. The line `wake: asleep on the bed until the user's click` is emitted at the moment the click wakes the character, but a backend read it as "still asleep, waiting for a click" and stayed silent on the day's…
5. [fix: make the test suite pass in any order and reject skipped or focused tests in lint](<https://github.com/yw0nam/YUI/pull/1460>)
   pull_request · 2026-10-15T07:57:24Z
   ## Summary The suite passed only in its default order. Three changes make it pass in shuffled order and stop a committed `.skip` or `.only` at lint; a fourth adds the rules for writing tests. 1. `vitest.config.ts`: `clearMocks: true`. Module-level `vi.fn()` doubles kept the call…
6. [\[spike\] Capability permissions that no window appears to use](<https://github.com/yw0nam/YUI/issues/1254>)
   issue · 2026-10-15T06:10:30Z
   ## Question to verify Are these permissions unused? - `src-tauri/capabilities/default.json`: `core:window:allow-set-cursor-position`, `allow-set-ignore-cursor-events`, `allow-start-dragging` - `src-tauri/capabilities/settings.json`: `core:window:allow-start-dragging` - `src-taur…
7. [chore: drop the main window's unused set-ignore-cursor-events permission](<https://github.com/yw0nam/YUI/pull/1459>)
   pull_request · 2026-10-15T06:10:26Z
   ## Summary The main window's capability drops `core:window:allow-set-ignore-cursor-events`. No frontend code calls the window plugin's `setIgnoreCursorEvents`: click-through goes through the app's own `set_click_through` command (`src/io/window/pet/hit-test.ts:160`), and the Rus…
8. [docs: the briefing page keeps one section order the user settles at install](<https://github.com/yw0nam/YUI/pull/1458>)
   pull_request · 2026-10-15T05:18:05Z
   ## Summary The briefing page's producer sections appear in one order on every day's page. The order is settled with the user at install (a new point 3 of § Install in `references/delivery/page.md`), carried in the render job's instruction, and applied to the `producers` sections…
9. [ci: run Python producer tests on Windows](<https://github.com/yw0nam/YUI/pull/1446>)
   pull_request · 2026-10-15T05:13:09Z
   ## Summary Add a bounded Windows CI job for the Python command path and daily briefing producer tests. The job runs on `windows-latest` with Node 22 and Python 3.13, then exercises the producer suite with both the platform default (`YUI_PYTHON` unset) and an explicit Python exec…
10. [fix: page-check rejects an entity escaped twice on the briefing page](<https://github.com/yw0nam/YUI/pull/1457>)
   pull_request · 2026-10-15T03:40:31Z
   ## Summary Briefing files carry third-party text that can already hold an HTML entity, such as `&amp;` inside a feed's URL. A render that escapes that text again puts `&amp;amp;` on the page, and the browser then opens the link with a broken query string. The render-job rule in …
11. [docs: the briefing page is written in a formal third-person register](<https://github.com/yw0nam/YUI/pull/1456>)
   pull_request · 2026-10-15T03:24:42Z
   ## Summary The briefing page is served publicly, so the text the render job writes on it reads as a published report. `references/delivery/page.md` § Render job now states the register: third person throughout, no second-person address, no name of the user, of the agent, or of a…
12. [\[feature\] Briefing delivery as a web page: a fixed HTML template the agent fills, served by static hosting of the published spool](<https://github.com/yw0nam/YUI/issues/1451>)
   issue · 2026-10-15T03:04:57Z
   ## Work description A third answer to Install step 6 of `integrations/skills/yui-daily-briefing/SKILL.md`: "a greeting with a link to a web page". The page is one HTML file per day, `<YYYY-MM-DD>/index.html`, written into the spool beside that day's markdown and pushed by `publi…
13. [feat: the daily briefing arrives as a web page per day, with a board of every day and page-check](<https://github.com/yw0nam/YUI/pull/1455>)
   feature · 2026-10-15T03:04:56Z
   ## Summary This PR adds a third answer to Install step 6 of the daily briefing skill: a greeting with a link to a web page for the day. Before the user's day starts, the agent fills a page with a fixed design from the day's briefings. Static hosting of the published spool serves…
14. [\[feature\] Nest the briefing spool by year, month and week, and give the published repository a fixed layout](<https://github.com/yw0nam/YUI/issues/1452>)
   issue · 2026-10-15T02:51:46Z
   ## Work description The spool, and so the published repository, lists one `<YYYY-MM-DD>/` folder per day at its root. After a year that is 365 folders side by side. The layout becomes: ``` .gitignore README.md the user's; publish leaves it alone index.html the board page, writte…
15. [feat: the briefing spool nests day folders under reports/ by year, month and week](<https://github.com/yw0nam/YUI/pull/1453>)
   feature · 2026-10-15T02:51:45Z
   ## Summary The briefing spool, and the repository `publish` pushes, now keeps each day under `reports/<YYYY>/<MM>/<Wn>/<DD>/`. Before this change, every day was a `<YYYY-MM-DD>/` folder at the root. `<Wn>` is the week of the month: `W1` covers days 1 to 7, `W2` 8 to 14, `W3` 15 …
16. [\[feature\] Publish the briefing spool to a git repository and hand the user a link in place of the spoken items](<https://github.com/yw0nam/YUI/issues/1448>)
   issue · 2026-10-15T02:07:12Z
   ## Work description The daily briefing is spoken item by item today. The user wants a greeting and a link to the day's report, and the report readable in a browser from anywhere. The spool already holds one markdown file per producer and day, and a git hosting service renders ma…
17. [feat: publish the briefing spool to a git repository and speak a link per day](<https://github.com/yw0nam/YUI/pull/1450>)
   feature · 2026-10-15T02:07:10Z
   ## Summary The daily briefing can be delivered as a greeting with one link per day to the published spool, in place of the items read out. - `briefing.py publish` stages every `<YYYY-MM-DD>/*.md` file of a spool that is its own git work tree, commits those paths only (`git diff …
18. [\[feature\] Architecture map of the push-transport plugin](<https://github.com/yw0nam/YUI/issues/1428>)
   issue · 2026-10-15T01:53:23Z
   ## Work description Add an architecture map of the push-transport plugin (`integrations/hermes/platform/yui/`) as a data file under the plugin's `docs/`, drawn by the client map's viewer, which gains a `?map=` query for a second data file in this work. The data file lists the pl…
19. [feat: architecture map of the push-transport plugin](<https://github.com/yw0nam/YUI/pull/1449>)
   feature · 2026-10-15T01:53:21Z
   ## Summary Adds an architecture map of the push-transport plugin (`integrations/hermes/platform/yui/`) in the client map's data format, drawn by the same viewer. 1. `integrations/hermes/platform/yui/docs/map.js` has 9 modules, 22 parts, 84 exchanges and 5 flows. The flows are th…
20. [\[feature\] Add time-based loneliness dynamics to the desire gate](<https://github.com/yw0nam/YUI/issues/1445>)
   issue · 2026-10-15T01:43:43Z
   <!-- from-natsume --> Opened by Natsume, the autonomous agent on profile natsume2. ## Work description Add a small, deterministic time-based affect update to the Hermes desire integration so that feelings such as `loneliness` can change even when no new event or held note exists…
21. [feat: the desire gate moves loneliness with time away and wakes the agent at each new level](<https://github.com/yw0nam/YUI/pull/1447>)
   feature · 2026-10-15T01:43:41Z
   ## Summary The desire gate now moves `loneliness` toward `user` with time since `last_interaction_at`, on every scheduled run, and wakes the agent once per new level. The change is wake case 3 in `integrations/hermes/desire/gate.py` (`loneliness_level`, `_loneliness_lines`), rec…
22. [fix: use Python executable on Windows](<https://github.com/yw0nam/YUI/pull/1398>)
   pull_request · 2026-10-15T01:33:24Z
   ## Summary Windows producer tests use the shared command-path convention instead of hardcoding the `py` launcher: `python` on Windows and `python3` elsewhere. `YUI_PYTHON` is an explicit override on every platform. The Windows default is `python` because the reported failure occ…
