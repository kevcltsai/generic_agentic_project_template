# Agent Roles

這些是邏輯角色，不代表每個角色都需要獨立 LLM session。

- `advisor.md`：需求理解與最小化。
- `pm.md`：重大功能與 Roadmap。
- `builder.md`：plan + implementation + validation。
- `reviewer.md`：必要時的獨立驗證。

一般情況優先讓同一個 Primary Working Agent 在不同 phase 切換 Advisor / PM / Builder；只有 Reviewer 的獨立性確實有價值時才分離 context。
