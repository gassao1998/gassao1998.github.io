# Changelog

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
