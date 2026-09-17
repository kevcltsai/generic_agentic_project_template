# Evals

此資料夾存放 agent behavior 的評估素材：scenarios、datasets 與 golden journeys。它們補足 deterministic tests 無法完整覆蓋的品質訊號。

- `scenarios/`：具有明確輸入、預期行為與判定方式的案例。
- `datasets/`：評估用的版本化資料集。
- `golden-journeys/`：端到端的重要使用者流程。

優先建立少量且高價值的案例。每個可重現的 production bug 或 agent regression，在可行情況下都應成為 scenario、golden journey 或 deterministic test。
