# Template Usage Guide

## 1. 新專案

先填 `IDEA.md`，用白話說明：為什麼想做、現在哪裡不順、希望帶來什麼體驗。

接著讓 Advisor 協助釐清，再形成 `PRODUCT.md`。產品方向穩定後，才補最小必要的 `ARCHITECTURE.md` 與 `ROADMAP.md`。

不要在 Day 0 預先建立所有可能用到的制度、文件或 specialist。

## 2. 新功能想法

使用者可以直接自然語言描述功能。Advisor 應：

1. 說明目前對需求的理解。
2. 找出真正要解決的問題。
3. 優先提出最小可用版本。
4. 明確區分「必要」與「可選 / Later」。
5. 不自行加入使用者沒有要求的功能。

需求確認後，若影響產品範圍或未來版本，再由 PM 更新 `PRODUCT.md` 或 `ROADMAP.md`。

## 3. Roadmap

PM 只管理重大功能：

- dependencies
- priority
- release grouping
- Current / Next / Later

不要加入 story points、sprint velocity、burndown 或其他沒有實際需要的 project-management ceremony。

## 4. 開始實作

當使用者明確說要開始做某項功能：

1. 將需求整理到 `work/CURRENT_TASK.md`。
2. Builder 建立短 plan。
3. Builder implementation + deterministic validation。
4. 一般 feature 或中高風險變更，必要時交給 Reviewer 做獨立檢查。
5. 完成後把真正需要長期保留的資訊寫回 PRODUCT / ROADMAP / DECISIONS。

不維護長期 task graveyard；歷史主要由 Git 保留。

## 5. Optional / Need-driven Modules

只有真的需要時才新增，例如：

- `docs/PLATFORM_REQUIREMENTS.md`：受到 Obsidian、Chrome Extension 等外部平台規範約束時。
- `docs/DESIGN_SYSTEM.md`：UI 規模已需要共同設計語言時。
- `evals/`：產品含非 deterministic AI 行為且 tests 不足時。
- specialist roles：只有重複出現的特定風險值得獨立角色時。

原則：**遇到真實問題再增加制度，而不是為完整而完整。**
