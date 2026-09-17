# Agentic Project Template — 使用手冊

## 這套 Template 的核心

這是一套讓人與 Agent 能長期合作的工作模型。它先保存「為何要做」，再把意圖變成產品定義、系統邊界、里程碑與可驗證的工作；不綁定任何 framework、語言或部署平台。

## 文件的順序與邊界

| 文件 | 回答的問題 | 不應放的內容 |
| --- | --- | --- |
| `docs/IDEA.md` | 我注意到什麼？為何在意？希望人有什麼體驗？ | 技術做法、功能清單、MVP、里程碑 |
| `docs/PRODUCT.md` | 為誰解決什麼問題？jobs、MVP、範圍、非目標與成功標準是什麼？ | 系統設計 |
| `docs/ARCHITECTURE.md` | 系統責任邊界與依賴方向是什麼？ | 取代產品決策 |
| `docs/ROADMAP.md` | 哪些產品成果先做、哪些後做？ | 每個小 task 的清單 |
| `docs/DECISIONS.md` | 為何作出重要決策？ | 日常狀態更新 |

`IDEA.md` 是 Human intent / source of intent。它必須能被完全不懂 code、system 或 infra 的人讀懂；技術字詞不是禁忌，但若必須用到，先換成日常語言說清楚。

## 新專案啟動流程

```text
IDEA.md
    ↓
Principal Advisor
    ↓
PM / Productization
    ↓
PRODUCT.md
    ↓
ARCHITECTURE.md
    ↓
ROADMAP.md
    ↓
第一條 Thin Vertical Slice
```

1. **寫 IDEA.md。** 用白話記下觀察、痛點、為何重要、期待改變與想像中的體驗。容許未知，不急著發明解法。
2. **Principal Advisor 檢視。** 釐清真正問題、假設、alternatives、trade-offs 與風險；建議 `PROCEED`、`PROCEED WITH CHANGES`、`RECONSIDER` 或 `NEEDS CLARIFICATION`。這不是把 IDEA 技術化。
3. **PM / Productization。** 以 IDEA 和 Advisor guidance 形成 `PRODUCT.md`：target users、problem、jobs、MVP、scope/non-goals、success criteria。保留來源與仍待驗證的假設。
4. **建立 ARCHITECTURE.md。** 只在產品方向明確後，先定義邊界與依賴方向，不必預先設計所有 class。
5. **建立 ROADMAP.md。** 依產品範圍、成功標準與依賴安排里程碑。
6. **建立最小驗證起點。** 先有少量高價值 deterministic tests、3–5 條 critical golden journeys（若適用），再完成第一條 Thin Vertical Slice。

## 日常開發流程

```text
User Request
    ↓
PM / Triage
    ↓
Principal Advisor
    ↓
Planner
    ↓
Implementer
    ↓
Reviewer
    ↓
PM / Closeout
```

- **PM/Triage**：分類、優先順序、大小、依賴、狀態與路由；不選技術設計。
- **Principal Advisor**：先看真實目標，再評估方向與風險。
- **Planner**：形成 scope/non-goals、步驟、acceptance criteria、validation 與風險；可用 `templates/TASK_SPEC.md`。
- **Implementer**：只做同意的範圍、補上驗證、回報證據與限制。
- **Reviewer**：獨立檢查需求、架構、regression、tests/evals、文件與完成標準，產出 `PASS` 或 `NEEDS FIX`。
- **PM/Closeout**：更新 status、dependencies、follow-up 與必要的 Roadmap。

## FAST PATH

簡單且低風險的 typo、小型文件修正、窄幅格式調整或明確 deterministic bug fix，可以使用 `FAST PATH`。PM、Advisor、Planner 的輸出可縮短，但仍要保留目的、範圍、驗證與 review 的責任。

## 何時更新哪份文件

- 人的原始動機、觀察或期待體驗改變：更新 `IDEA.md`，再重新檢視 PRODUCT。
- 使用者、問題、MVP、範圍或成功標準改變：更新 `PRODUCT.md`，必要時調整 Roadmap/Architecture。
- 系統邊界或依賴方向改變：更新 `ARCHITECTURE.md` 與 `DECISIONS.md`。
- 里程碑順序改變：更新 `ROADMAP.md`。
- 專案工作規則或角色交接改變：更新 `AGENTS.md` 或 `agents/` contracts。

## 驗證原則

能 deterministic 驗證的行為，優先使用 tests、schema/state assertions、typecheck、lint 與 build checks；evals 適用於 tool selection、context use、模糊需求處理、agent behavior 與多步使用旅程。可重現的 production bug，應在可行情況下轉為 regression test 或 eval。

## 最小日常指令

```text
Follow this repository's AGENTS.md and agent contracts.
For a new project, preserve IDEA.md as the human source of intent and use the project-initiation flow.
For daily requests, perform proportional PM triage and Principal Advisor assessment first.
Use FAST PATH only for trivial low-risk work; retain validation and review.
```
