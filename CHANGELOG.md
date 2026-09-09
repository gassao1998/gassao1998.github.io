# Changelog

## 2026-09-09
- **佔位內容清空，換上真作品**（owner：「專案導覽頁面整理一下，有些用不到了，新寫的論文放上來」）。
- `#writing`：三筆假文案 → **兩筆論文條目**（碩論題目、研究問題章）。⚠️ `thesis` 與 `thesis-wiki`
  兩個 repo 都是 **private**，所以條目**不放連結**（不用 `href="#"` 空殼）。
- `#code`：三張假卡 → **三個真專案**——東京防災互動地圖（唯一有公開連結：
  https://tnf-einfo.github.io/einfo-widgets/ ，已驗證 repo 為 PUBLIC 且 Pages 有效）、
  颱風路徑短影音自動產製、論文文獻庫工具鏈（後兩者私有、不放連結）。
- `#photography`：六張「照片」佔位磚拿掉（`images/` 根本還沒建），改成一行「照片整理中」；
  gallery 的 CSS/JS 全部保留，原地留註解說明怎麼換回來。
- footer：Instagram／Threads 兩個空殼連結刪掉（不知道真網址），GitHub 換成真的
  https://github.com/gassao1998 。
- 新內容一律**中英成對**（`t-zh`/`t-en`），避免切 EN 時露出中文；檔頭註解同步改寫。
- 自驗：`TODO` 殘留 0、標籤無未閉合／多餘結束、`href="#"` 只剩註解裡的說明文字。

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
