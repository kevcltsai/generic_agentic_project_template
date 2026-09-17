# Architecture

只記錄 Agent 工作時真的需要知道的系統邊界、重要資料流與 constraints。不要把 codebase 翻譯成長篇文件。

## Components / Boundaries

<!-- 例：UI -> Application -> Domain -> Adapters / Infrastructure -->

## Important Data Flow

<!-- 只畫或描述關鍵流程。 -->

## Constraints

<!-- 目前真正會影響 implementation 的限制。 -->

## Rules Worth Preserving

- UI 不應承載核心 domain logic。
- 外部 API / model / database 優先透過清楚的 boundary 或 adapter 隔離。
- 不為未確定的未來需求預先複雜化架構。

重要「為什麼」請記到 `DECISIONS.md`。
