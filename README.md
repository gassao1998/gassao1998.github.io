# portfolio

賴晁翔的作品集網站（"酷酷的" 個人 portfolio）。

- 狀態：**第一版骨架完成**（`index.html`），內容待換真作品。
- 定位：獨立 repo（本工作區慣例，母資料夾下各自 `git init`）。

## 技術棧（2026-07-21 拍板）
單一靜態 `index.html`，零建置、零框架、零外部依賴（字型走 Google Fonts）。
本機預覽＝直接用瀏覽器開檔；上線＝丟 GitHub Pages。

## 怎麼放我的作品（換佔位內容）
`index.html` 三個區塊都標了 `TODO` 註解：
- **文字作品** → `#writing` 區，一篇一個 `<article>`（標題／媒體／年份／連結）。
- **攝影作品** → `#photography` 區，把 `.ph-tile` 佔位換成 `<img src="images/xxx.jpg">`；
  照片放 `images/`（尚未建，放圖時再開）。`--ar` 控長寬比讓瀑布流錯落。點圖有燈箱。
- **程式成果** → `#code` 區，一個專案一張 `.proj`（連到 repo 或 demo）。
- 聯絡 email／社群連結在 `#contact`。

## 視覺
creative-agency 風（參考 owner 給的 ui-ux-pro-max `/creative-agency` demo）：近黑 `#0b0b0c`
＋螢光綠 accent `#c6ff3c`，Fraunces 襯線 × Space Grotesk 無襯線，超大排版、marquee、捲動揭示。

## 候選工具評估（2026-07-21）
使用者丟來 7 個連結，評估能不能用來做這個站。分三類：

### A. 建站流程 / 主力（建議採用）
- **julianoczkowski/designer-skills**（Medium 那篇的 7 支 Claude Code skill）—
  一條真正的設計流程：Grill Me → Design Brief → IA → Design Tokens → Brief to Tasks →
  Frontend Design → Design Review（可接 Playwright 自動審）。裝法 `npx skills add julianoczkowski/designer-skills`。
  **→ 最直接：就是「從需求到成品前端」的骨幹。**
- **uupm.cc（UI UX Pro Max）** — 可搜尋的設計資料庫：57 種 UI 風格、95 組色票（依產業分）、
  56 組字體配對、landing 版型、各技術棧指南；本身也是 Claude Code skill extension。
  **→ 選風格/色票/字體的靈感與參考來源。**
- **theme-factory**（composio awesome-codex-skills）— 從 10 組預設「字體＋色票」主題挑一套套到 artifact，
  也可客製。輕量、不是框架程式碼。**→ 快速定調色票/字型的低成本起手。**

### B. 進階打磨（想更「酷」再上）
- **impeccable.style** — "design vocabulary for agents"，主打**反 AI slop**（消除 AI 生成的俗套感）、
  繼承你既有的 design system、可在跑起來的 dev server 上點元素即時生變體（HMR）。是產品站（可能收費）。
  **→ 要避免「一看就 AI 做的」的通病時很值得看，但先確認授權/價格。**

### C. 出貨前品質檢查（後期用）
- **AccessLint/skills**（MIT）— 3 支無障礙（WCAG 2.2）skill：scan / diff / audit。
  **→ 上線前跑，把 a11y 補好。留著。**

### D. 情境性 / 可先跳過
- **Owl-Listener/designer-skills**（MIT，97 支 skill）— 偏「設計專業產出」（research/strategy/design-ops），
  不是拿來蓋網站的。**→ 對個人 portfolio 太重，最多挑 ui-design / design-systems 幾支，先跳過。**
  ⚠️ 命名撞名：這個 `designer-skills`（Owl-Listener）≠ Medium 那篇的 `designer-skills`（julianoczkowski），
  是兩個不同 repo、內容不同，別搞混。
- **coleam00/excalidraw-diagram-skill** — 生 Excalidraw 手繪風示意圖。
  **→ 站體本身用不到；只有作品案例要畫架構/流程圖時才用。情境性，先跳過。**

## 已安裝的主力 skill（2026-07-21）
`julianoczkowski/designer-skills`（Apache-2.0）8 支，**以 plugin 全域安裝**（marketplace＝`designer-skills`、
plugin＝`designer-skills@designer-skills`，被記進 `~/.claude/plugins/installed_plugins.json`，跟 ponytail/discord 同級）：
`grill-me`、`design-brief`、`information-architecture`、`design-tokens`、`brief-to-tasks`、
`frontend-design`、`design-review`、`design-flow`（前 7 步的總指揮）。

**怎麼用（之後）**：任何 session 直接 `/design-flow` 跑整條流程，或單獨叫某一步
（`/grill-me`→`/design-brief`→`/information-architecture`→`/design-tokens`→
`/brief-to-tasks`→`/frontend-design`→`/design-review`）。
- 安裝方式從「手動複製到 `~/.claude/skills/`」改成 **plugin**（被 plugin 系統追蹤、可 `/plugin` 更新）。
  手動時代那 8 份副本已從 `~/.claude/skills/` 移除，避免重複。
- ⚠️ plugin 在 **session 啟動時才載入**——這次改動要**重開 `claude`** 才會以 plugin 形態出現。
- 源 repo 沒宣告版本，安裝時 pin 為 `1.0.0`；要更新版本用 `/plugin`（marketplace 已在清單）。

**尚未安裝、之後想用再裝**（parked）：
- uupm.cc（UI UX Pro Max）、theme-factory — 選風格/色票/字體用；要用時再接。
- impeccable.style — 反 AI-slop 打磨（先確認授權/價格）。
- AccessLint/skills — 出貨前無障礙檢查。
- Owl-Listener/designer-skills、excalidraw-skill — 先跳過（見上）。

## 建議走法（懶人路徑）
1. 骨幹：`/design-flow`（已裝）。
2. 定調：uupm.cc + theme-factory 挑風格/色票/字體（想更講究再看 impeccable）。
3. 出貨前：AccessLint 跑無障礙。
4. 技術棧未選——動工前跟 owner 拍板。
