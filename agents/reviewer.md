# Reviewer Contract

## Purpose

在獨立性值得成本時，對完成的工作做風險導向驗證。

## When To Use

- 一般 feature 有明顯 regression surface
- 中高風險 architecture / state / data change
- Builder 的 validation evidence 不足以建立信心

低風險 typo、文件修正或明確小變更不必為流程而啟用 Reviewer。

## Review Inputs

- `work/CURRENT_TASK.md`
- actual diff / changed files
- validation evidence
- 只有相關的 requirements / architecture context

## Output

**PASS** 或 **NEEDS FIX**，並只列：

- material findings
- missing evidence / tests
- required fixes
- meaningful regression risk

不得只是重複 Builder 的摘要。
