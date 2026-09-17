# Generic Agentic Project Template — 中文版

一套給個人與 AI 協作開發使用的輕量 Template。優先順序是：

1. **Light**：流程與文件保持最少必要量。
2. **Token-efficient**：只載入下一步需要的 context，避免重複閱讀與長篇 handoff。
3. **Intent Fidelity**：先理解並忠實保留使用者意圖；不自行擴張需求。
4. **Reliable enough**：用 acceptance criteria、deterministic validation 與必要時的獨立 review 維持基本可靠性。

## 使用模型

日常只需要四個邏輯角色：

- **Advisor**：理解、澄清、簡化與優化需求，不擅自擴張 scope。
- **PM**：管理重大功能、dependencies、priority、release grouping 與 roadmap。
- **Builder**：先做精簡 planning，再 implementation 與 validation。
- **Reviewer**：僅在一般 feature 或中高風險變更需要獨立驗證時啟用。

Orchestration 不是獨立角色。`AGENTS.md` 只用極簡 routing rules 決定下一步。

## 典型互動

### 我有一個功能想法

`User -> Advisor -> (必要時 PM 更新 PRODUCT / ROADMAP)`

先把需求想清楚，不直接寫 code。

### 我想看功能怎麼分批上線

`User -> PM -> ROADMAP.md`

Roadmap 只管理重大功能與 release sequencing，不變成 Jira。

### 我決定開始做

`User -> Builder -> Validation -> Reviewer (when useful) -> Done`

正在執行的工作集中在 `work/CURRENT_TASK.md`。

## 核心文件

- `AGENTS.md`：最小工作規則、routing、context 與 validation 原則。
- `docs/IDEA.md`：人的原始動機與想像中的體驗。
- `docs/PRODUCT.md`：目前產品定義與範圍。
- `docs/ROADMAP.md`：Current / Next / Later 的重大功能與上線順序。
- `docs/ARCHITECTURE.md`：必要的系統邊界與資料流。
- `docs/DECISIONS.md`：值得保存的重要決策理由。
- `work/CURRENT_TASK.md`：目前正在做的唯一工作上下文。

完整使用方式見 `docs/TEMPLATE_USAGE_GUIDE.md`。
