# 架構

## 目的

本檔在 `IDEA.md` 與 `PRODUCT.md` 已形成方向後，記錄系統的責任邊界與依賴方向。技術決策的理由請記錄於 `DECISIONS.md`；不要用架構選擇改寫人的原始意圖或產品範圍。

## 預設分層

```text
UI / Interface
    ↓
Application / Orchestration
    ↓
Domain Logic
    ↓
Tools / External Adapters
    ↓
Storage / Infrastructure
```

## 邊界規則

- UI 不直接承載 business logic。
- Domain logic 不依賴具體 UI、vendor SDK 或 infrastructure。
- 外部 API、LLM、database 與 filesystem 透過 adapters 存取。
- Orchestration 協調流程，但不應吸收所有 domain rules。
- 依賴方向由外層指向內層；內層不得反向依賴外層。

## 專案專屬決策

<!-- 在 PRODUCT.md 明確後，補上實際元件、資料流、interfaces 與禁止反轉的 dependency directions。 -->
