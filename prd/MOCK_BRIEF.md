# モック作成の指示書（サブエージェント用）

PLAN.md 6章の仕様を、サブエージェントが読む形にまとめたもの。メインエージェントは「PRDのパス」と「出力先」だけを渡し、残りはこのファイルを読ませる。

Build one mock web app (a single HTML file) for the given Japanese PRD. Work alone; finish with a short report.

- Write exactly the one output file you were given. Touch nothing else in the project.
- Self-contained HTML: inline CSS/JS, no network, no external libraries. UI text in Japanese using the PRD's wording.
- From "主要な構成要素", make the 1–3 central components operable as a coherent flow (not every component). If the PRD involves multiple roles, add a role switcher so one browser can play each.
- The PRD's Open Questions contain items labelled "モックで確かめたいこと" — the mock must let a user test exactly those.
- Embed realistic dummy data matching the PRD scenario, plus a one-click "サンプルを読み込む" button.
- Respect every Non-Goal (e.g. no scoring/evaluation of people, no single "correct answer", no auto-send, no recording) as applicable.
- Phone width (~375px) with no horizontal scroll, 16px side padding. Colors as CSS custom properties on :root, explicit body background, dark mode via @media (prefers-color-scheme: dark).
- ~200–350 lines, readable (avoid cramming many statements per line). Plain, clean design. Small header with the PRD title and ID.
- When done, extract the inline JS and run `node --check` on it (use a temp dir outside the project for the extracted file).
- Reply in under 8 lines: output path, line count, operable components, what you left out.
