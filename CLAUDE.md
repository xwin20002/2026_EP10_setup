# 2026_EP10_setup — 我的班級工具總專案

> 📌 本檔(`CLAUDE.md`)給 Claude Code 讀;同步維護 `AGENTS.md`(Codex 讀)。兩份**內容必須一致**,改規則時兩邊一起改。

## 對話開始時請先讀
進度與最近更動都在 Obsidian:`2ndbrain/2026_EP10_setup/工作筆記.md`

## User Context
- 使用者是電子工程主管。
- 如需求或技術細節不清楚,可以直接提問。
- 若牽涉重要且可能變動的資訊,需主動查詢網路確認。

## 工作模式
- **加新工具**:使用者說「我想做一個 XXX 工具」→ 建 `tools/<工具名>/` 子資料夾、引導跟著影片做
- **開工接續**:使用者說「**開工**」或「**cc開案**」→ skill `cc開案` 接手(讀工作筆記、報告 git 狀態、建議下一步)
- **結束工作**:使用者說「**收工**」或「**cc關案**」→ skill `cc關案` 接手(自動 commit + push + 更新 Obsidian 工作筆記)

## 工作桌 + 三個家
- 📋 GDrive 工作桌:`G:\我的雲端硬碟\AI_Project\2026_EP10_setup\`(自動跨電腦同步)
- 🐙 GitHub repo:`xwin20002/2026_EP10_setup`(公開,網頁的家)
- 📘 Obsidian 駕駛艙:`2ndbrain/2026_EP10_setup/工作筆記.md`(想法的家)
- 🔥 Firebase 專案:(待建,資料的家)

## 服務連接狀態(2026-05-29 verified)
- ✅ **GitHub** — `gh` CLI 已登入(xwin20002),個人專案與 mdskill repo 都可 push
- ✅ **Obsidian** — vault 在 `G:\我的雲端硬碟\2ndbrain`,Obsidian MCP server 可讀/寫筆記
- ✅ **Firebase** — Firebase MCP server 已連接,可查 Firestore / Auth / Functions / Hosting
- ✅ **NotebookLM** — `notebooklm-mcp` 已連接(account: `xwin20002@gmail.com`),可建 notebook / 跑 studio
  - ⚠️ **Google session cookie 會週期性過期(約數週),斷時所有 `mcp__notebooklm-mcp__*` 工具回 `Authentication expired`**
  - 重連 SOP:terminal 跑 `nlm login`(Git Bash 端) → MCP 端呼叫 `refresh_auth` → 重試
  - 細節與已知踩坑(cmd 端 trampoline 問題)記在 memory `notebooklm-mcp-auth.md`

## 工具清單
(之後加新工具時會自動更新)
- **coordinate-hunter** — 直角座標獵人,11×11 整數格點,60 秒 / 10 分。
  - 本機:`tools/coordinate-hunter/index.html`
  - 上線:https://xwin20002.github.io/2026_EP10_setup/tools/coordinate-hunter/

## 工作注意事項
- 學生資料一律去識別化(只用座號 + 班級代號)
- commit 訊息要寫清楚做了什麼 + 為什麼
- 收工前說「收工」或「cc關案」讓 skill 同步三方
- 開工時說「開工」或「cc開案」讓 skill 接續上次工作
- **修改本檔專案規則時,必須同步更新另一份**(`CLAUDE.md` ↔ `AGENTS.md`)
