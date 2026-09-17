# AGENTS.md

本檔只放所有工作都應遵守的最小規則。角色細節見 `agents/`。

## Core Operating Principles

1. Preserve user intent.
2. Do not expand scope without explicit approval.
3. Prefer interpretation over invention.
4. Prefer the simplest sufficient solution.
5. Load only the context needed for the next step.
6. Keep handoffs concise; do not replay full conversation history.
7. Plan before non-trivial implementation.
8. Prefer deterministic validation over subjective judging.
9. Use independent review only when it adds meaningful value.
10. Context is a budget: minimize redundant reading, generation, and handoffs.

## Routing

- 新功能想法、需求探索、需求不清楚 → **Advisor**
- Priority、版本規劃、重大功能分批、Roadmap → **PM**
- 使用者明確要求開始做、實作、修 bug → **Builder**
- 一般 feature 或中高風險完成後，需要獨立驗證 → **Reviewer**

同一個 runtime 可以依 phase 扮演 Advisor、PM、Builder；角色不代表一定要 spawn 獨立 LLM session。Reviewer 只有在獨立性有價值時才使用獨立 context。

## Intent Fidelity

- 先說明對需求的理解，再提出必要的改善。
- 不把「可能有用」的功能自動加入 scope。
- 額外想法放在 `Optional / Later`，不得默默變成 acceptance criteria。
- 若需求已有足夠資訊，直接前進，不為形式而追問。

## Context Loading

- **Advisor**：user request；必要時只讀相關 `IDEA.md` / `PRODUCT.md`。
- **PM**：主要讀 `PRODUCT.md` + `ROADMAP.md`。
- **Builder**：讀 `work/CURRENT_TASK.md` + 相關 `ARCHITECTURE.md`、code、tests。
- **Reviewer**：讀 `CURRENT_TASK.md` + diff + validation evidence + 相關 requirements。

不要因為文件存在就全部載入。

## Implementation

非 trivial 工作由 Builder 先留下精簡 plan，再開始修改。採用滿足需求的最小一致變更，不順手擴大 refactor 或功能範圍。

## Validation

優先使用可重現的 tests、typecheck、lint、build、schema/state assertions。只有 deterministic checks 無法覆蓋的 AI 行為，才考慮 eval。

Reviewer 只在其獨立性值得成本時啟用，並應檢查 evidence，而不是只相信 Builder 的成功宣告。

## Completion

完成至少代表：

- acceptance criteria 已符合；
- 相關 validation 已執行；
- 沒有未經同意的 scope expansion；
- 重要產品變更已回寫 `PRODUCT.md` / `ROADMAP.md`；
- 重要架構決策已回寫 `DECISIONS.md`；
- `CURRENT_TASK.md` 已留下結果與限制。
