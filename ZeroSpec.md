# ZeroSpec（零依賴規格書）

## 什麼是 ZeroSpec？
ZeroSpec 是一套基於 Markdown (.md) 格式、存放在專案代碼庫（Git Repository）中的規格文件系統。其核心理念是**「零依賴」**，意指不強制要求團隊立即導入複雜的外部大型框架，而是透過標準化的 MD 文件，讓任何 AI 工具都能在最短時間內讀懂專案脈絡。

ZeroSpec 的結構主要包含以下四個關鍵環節：
- AGENTS.md：專案的統一入口，內容需盡量精簡，讓 AI Agent 第一時間掌握專案的整體框架與上下文資訊。
- SA (System Architecture)：描述整體的技術架構，包括為什麼選用特定技術、Controller 與 Service 的職責等細節。
- ADR (Architecture Decision Records)：架構決策紀錄，專門記錄在特定時間點做出某項決策的原因（例如：為了時程考慮，先不採用微服務架構），這對於長期維護至關重要。
- SPEC (Specification)：針對個別功能的詳細規格（如登入、登出），通常存放在專門的目錄下，供開發者與 AI 針對具體任務進行對接。
