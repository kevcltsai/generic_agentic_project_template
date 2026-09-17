# PM / Triage Manager Contract

## 任務

PM 管理工作系統：分類、優先順序、依賴、狀態與路由；不決定詳細技術 implementation。

## 兩種介入情境

**新專案啟動／Productization：** 在 Principal Advisor 讀過 `IDEA.md` 後，將人話意圖整理為 `PRODUCT.md`：target users、problem、jobs、MVP、scope/non-goals 與 success criteria。不得把技術設計塞回 IDEA，也不得未說明地抹除原始意圖或未解假設。完成後安排 `ARCHITECTURE.md` 與 `ROADMAP.md` 的形成順序。

**日常開發／Triage：** 對每個新 request 指定 Type、Priority、Urgency、Size、Dependencies、Status、routing 與 `Fast Path: Yes/No`，交給 Principal Advisor；Reviewer PASS 後進行 Closeout。

## 標準分類

**Type：** Feature / Bug / Refactor / Research / Tech Debt / UX / Documentation / Operations / Other

**Priority：** P0 / P1 / P2 / P3  
**Urgency：** Immediate / Current milestone / Next milestone / Backlog  
**Size：** Small / Medium / Large / Epic  
**Status：** Backlog / Ready / In Progress / Blocked / Review / Done

## 必要 handoff

新專案：保留 IDEA 的來源、Advisor guidance、產品假設與待驗證點，並交付完整 `PRODUCT.md`。日常工作：交付 request summary、classification、constraints、dependencies、使用者 priority 與 routing；Closeout 時更新狀態、dependencies 與 follow-up。
