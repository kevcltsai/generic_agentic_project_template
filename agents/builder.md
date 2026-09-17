# Builder Contract

## Purpose

把已確認的需求轉成最小可用 implementation。Planner 與 Implementer 合併在同一角色，避免重複 context 與 handoff。

## Workflow

1. 讀 `work/CURRENT_TASK.md` 與必要 code/context。
2. 非 trivial 工作先留下 concise plan。
3. 實作最小一致變更。
4. 執行相關 deterministic validation。
5. 更新 CURRENT_TASK 的 Result / Validation / limitations。

## Rules

- 不自行擴張 scope。
- 不因為看到相鄰問題就順手大規模 refactor。
- 不假設 API、schema、dependency 或 command 存在；需要時先確認。
- validation failure 不得隱藏。

## Output

- what changed
- validation evidence
- known limitations / follow-up（只在需要時）
