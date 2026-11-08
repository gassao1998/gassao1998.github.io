# Changelog

## 2026-11-08（第五版）
- `ascii-cave/` 換成第五版（原始碼 repo `70c3e7f`）：手改成前臂中立位的握法（拇指在上、手心朝畫面中央），鏡面中央的塔改成吊在三腳的環形接頭上（兩隻白色拱腳加一條鏽褐色桁架），碗面改成同心環的方板。只換 `index.html`，貼圖沒變。

## 2026-11-08（第四版）
- `ascii-cave/` 換成第四版（原始碼 repo `3bf8ffe`）：點擊轉視角、手照實拍握法、貓改成橫躺在拱上、洞口改成只圍著拱門的端牆、走道換成紅色花紋鋼板與鋼管欄杆、鏡面中央換成沙漏形白塔，隧道原型查證是葉里溫兒童鐵道並改成 750 mm 窄軌。`cat-arch.jpg` 換成 `cat-band.jpg`，預覽圖換成走道上看鏡面的畫面。

## 2026-11-07（第三版）
- `ascii-cave/` 換成第三版（原始碼 repo `2480c58`）：手改用 CC0 的 WRAD ARMS 手臂模型、字元格再細一倍、鐵軌做舊、塗鴉 35 張、投影的貓與控制室壁畫、每 156 公尺出洞走一段 ROT-54 的走道。`assets/` 整個換新，多了 `models/arms.glb`，舊的 `cat.jpg` 刪掉。

## 2026-11-07
- 新增 `ascii-cave/`：ASCII 字元畫的鐵道隧道互動作品，網址 https://gassao1998.github.io/ascii-cave/ ，還沒連進首頁。原始碼在私人 repo `gassao1998/ascii-cave`（`d0404eb`），這裡只放網頁要用的 `index.html`、`preview.jpg` 與 11 張塗鴉貼圖。

## 2026-11-05
- commit 訊息改寫：舊 commit 拿掉誰要求、誰決定的寫法，已推上 GitHub 的只改標題，檔案內容不動。新舊編號對照在 `docs/commit-map-2026-11-04.tsv`，舊歷史在 tag `archive/pre-rewrite-2026-11-04/<分支>`。
- HANDOFF 與 README 的同樣寫法拿掉，待辦改寫成要做的動作。

## 2026-07-21
- 開 repo（`git init`），建 README + CHANGELOG。
- 評估 owner 丟來的 7 個設計工具/資源連結（見 README「候選工具評估」），分主力/打磨/QA/可跳過四類。
- 尚未選技術棧、尚未動工。
- 裝主力 skill：`julianoczkowski/designer-skills`（Apache-2.0）8 支 vendored 進 `.claude/skills/`
  （grill-me / design-brief / information-architecture / design-tokens / brief-to-tasks /
  frontend-design / design-review / design-flow）。專案層 scope、隨 repo 走；用法見 README「已安裝的主力 skill」。
  其餘 6 個候選（uupm.cc、theme-factory、impeccable、AccessLint、Owl-Listener、excalidraw）記在 README，之後要用再裝。
- 改成**全域安裝**：8 支移到 `~/.claude/skills/`（任何目錄可用），移除專案層 `.claude/` 那份避免重複。
  代價：不隨此 repo clone 走、不會自動更新（要追版改用 plugin marketplace，指令見 README）。
- 再改成 **plugin 全域安裝**：手動接好 marketplace（`designer-skills`）＋ plugin
  （`designer-skills@designer-skills`，pin 1.0.0）進 `~/.claude/plugins/`，登進 installed_plugins.json；
  移除手動 `~/.claude/skills/` 那 8 份副本。動 plugin 設定前備份了 known_marketplaces/installed_plugins。
  **需重開 `claude` 才會以 plugin 形態載入。** 好處：被 plugin 系統追蹤、可 `/plugin` 更新。
- 技術棧拍板：**單一靜態 `index.html`，零建置、GitHub Pages 直接上**（YAGNI，portfolio 這尺寸不上框架）。
- 建第一版 `index.html`（creative-agency 風，參考 owner 給的 ui-ux-pro-max /creative-agency demo）：
  近黑底＋螢光綠 accent、Fraunces 襯線 × Space Grotesk 無襯線、超大編輯排版、kinetic marquee、
  捲動揭示（IntersectionObserver）、攝影瀑布流＋燈箱。三區塊 文字／攝影／程式＋聯絡，
  內容全為標 TODO 的佔位（待換真作品）。prefers-reduced-motion 有處理。
- **v2 改「暗房編輯風 Darkroom Editorial」**（apple/artifact-design skill 指出 v1 的近黑+螢光綠+Space Grotesk+
  01/02/03 正是最典型 AI 罐頭臉；改走更貼「記者×攝影×開發」的方向）：單一暗色世界（不做亮色主題＝暗房質感的
  刻意選擇）、暖近黑 `#141110`＋安全燈琥珀 `#d98a4e`、Instrument Serif 標題 × Space Mono（照片 EXIF/程式標籤）×
  系統襯線內文、整頁淡底片顆粒（inline SVG 噪點）、hero 底片計數細節、拿掉 01/02/03 編號。
  文字＝雜誌目錄式、攝影＝雙欄大圖＋EXIF 說明＋燈箱、程式＝mono 卡。內容仍佔位。
- **v3 改「明亮 creative-agency」**（owner：暗房版「太怪了」，要照原本 ui-ux-pro-max /creative-agency 範例的類型走）：
  白底、Bricolage Grotesque 粗體大字、鮮明橘 `#ff4a1c`、圓角卡片＋hover 浮起、跑馬燈、「我能做什麼」三卡、
  橘色大 CTA 區塊；單一亮色世界。（無法擷取該 demo 實際畫面——SPA＋瀏覽器外掛未連——故照 creative-agency
  類型做，待 owner 給截圖再一比一。）另：`review_app.py` 已加 `/portfolio` 路由供這頁（tailnet 可看）。
- **修 RWD**：補上漏掉的 `<meta name="viewport">`（＋`charset=utf-8`）。少了它手機會用 ~980px 假視窗把整頁縮小
  → owner 手機看字太小的根因。桌面本來就正常，故非字級問題而是缺 viewport meta。
- 手機版 hero 標題會蓋到右上角中英切換鈕：≤680px 時 header 加 `padding-top:4.5rem` 把標題壓到鈕下方。
- 「我能做什麼」三張能力卡拿掉 `01/02/03` 編號（owner：卡片別搞成三行、兩行就好）→ 每卡剩標題＋敘述兩行；順手移除 `.cap .no` 樣式、h3 top margin 歸零。
- 程式成果的技術標籤 pill 加回外框（`.tags span` 補 `border:1px solid var(--line)`）——原本只靠填色、在米色 alt 區塊上像沒框（owner 回報）。
- **公開上線**：推上 GitHub `gassao1998/gassao1998.github.io`（公開 repo），GitHub Pages 從 master 根目錄建置、HTTPS，網址 **https://gassao1998.github.io/**。用帳號名當 user-site＝根網域最乾淨。之後 push 即自動重建更新。內容仍多為 TODO 佔位。
