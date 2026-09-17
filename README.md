# Generic Agentic Project Template

這是一個可重複使用、用於 agentic 軟體專案的 Day-0 骨架。不綁定 framework、語言或部署平台。

## 兩套流程

### 新專案啟動

`docs/IDEA.md -> Principal Advisor -> PM / Productization -> docs/PRODUCT.md -> docs/ARCHITECTURE.md -> docs/ROADMAP.md -> 第一條 Thin Vertical Slice`

先以白話記下人想解決的事與理想體驗；Advisor 協助檢視方向，PM 將意圖產品化。產品定義清楚後，才建立架構邊界、里程碑與驗證起點。

### 日常開發

`User Request -> PM/Triage -> Principal Advisor -> Planner -> Implementer -> Reviewer -> PM/Closeout`

簡單、低風險需求可用 `FAST PATH` 壓縮 triage、advice 與 planning，但不能省略 validation。

## 文件順序與邊界

- `docs/IDEA.md`：Human intent / source of intent；以完全白話說明為什麼在意、觀察到的問題與想要的體驗。
- `docs/PRODUCT.md`：目標使用者、問題、jobs、MVP、範圍、非目標與成功標準。
- `docs/ARCHITECTURE.md`：系統責任邊界與依賴方向。
- `docs/ROADMAP.md`：產品化後的里程碑與先後順序。
- `docs/DECISIONS.md`：重要決策與理由。

## 專案結構

- `AGENTS.md`：agent 的工作規則。
- `agents/`：角色責任與 handoff contracts。
- `docs/`：意圖、產品、架構、Roadmap、決策與完成標準。
- `evals/`、`tests/`、`templates/`、`reference/`、`src/`、`scripts/`：驗證、範本、參考資料、程式與協助工具。

完整流程請讀 `docs/TEMPLATE_USAGE_GUIDE.md`。複製模板後，移除不適用的資料夾即可，不要為保留結構而虛構需求。
