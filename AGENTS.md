# AGENTS.md

## 用途

本檔定義 AI agents 在此 repository 工作時的預設規則。

## 先判斷是哪一種流程

**新專案啟動**使用：`IDEA.md -> Principal Advisor -> PM / Productization -> PRODUCT.md -> ARCHITECTURE.md -> ROADMAP.md`。`IDEA.md` 是 Human intent / source of intent，應以白話保留；PM 才把它轉為產品定義。

**日常開發**使用：`User Request -> PM/Triage -> Principal Advisor -> Planner -> Implementer -> Reviewer -> PM/Closeout`。每個需求都要有比例適當的 PM triage 與 Advisor assessment；簡單、低風險工作可用 `FAST PATH`。

## 開始前

- 日常工作先讀 `README.md`、`docs/PRODUCT.md`、`docs/ARCHITECTURE.md` 與適用的 `docs/DECISIONS.md` ADRs；若工作影響產品意圖或新專案方向，也讀 `docs/IDEA.md`。
- 新專案先讀並保留 `docs/IDEA.md` 的人話意圖，再進行 Advisor 與 Productization。
- 先辨識 acceptance criteria；不得假設 API、檔案、命令、schema 或 dependencies 存在。

## 角色與實作

PM 管分類、優先順序、依賴與路由；Advisor 檢視真正目標、方向、alternatives、trade-offs 與風險，並建議 `PROCEED`、`PROCEED WITH CHANGES`、`RECONSIDER` 或 `NEEDS CLARIFICATION`。Planner 在方向確定後定義 goal、scope/non-goals、步驟、acceptance criteria、validation 與風險。

採用滿足任務的最小一致變更，不默默擴張 scope。UI、orchestration、domain logic、tool adapters 與 infrastructure 必須分離；secrets 不進 source control。

## 驗證與完成

可行時優先執行 typecheck、lint、tests、schema/state assertions 與 build checks；只有 deterministic assertions 不足時才使用 LLM evaluation。完成前驗證 acceptance criteria、檢查 regression、同步必要文件。非簡單工作經 Reviewer 獨立驗證後，才由 PM Closeout 更新狀態、dependencies 與 follow-up。完整標準見 `docs/DEFINITION_OF_DONE.md`。
