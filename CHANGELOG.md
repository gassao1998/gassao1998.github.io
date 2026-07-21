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
