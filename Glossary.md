Glossary （術語表，名詞解釋）

# GPT
### Bounded Text Updates（有界文字更新）
> Bounded Text Updates（有界文字更新） 是近年 Agent 與 Prompt/Skill 優化領域的重要概念，尤其是 Microsoft Research 的 SkillOpt 核心機制之一。簡單來說：限制 AI 每次只能對技能文件（Skill Document）做有限幅度的文字修改，而不能任意大幅重寫整份文件。
> 總結：Bounded Text Updates（有界文字更新）就是限制 AI 每次只能對 Prompt 或 Skill 文件做少量、可控的修改，類似深度學習中的 Learning Rate 控制，藉此避免技能漂移、提升穩定性，並讓 Agent 的技能能夠逐步而可靠地進化。
> 這種更新等於徹底阻止了大模型那種一言不合就重寫全文的毀滅性衝動。
- 為什麼需要這個機制？
  ```
  假設你有一份 Agent 技能：
  # 故障排除技能
  1. 先收集錯誤訊息
  2. 查詢系統日誌
  3. 驗證修正結果 ...

  如果讓 AI 自由修改，可能會變成：
  # 新技能
  直接猜測問題原因
  然後提供解法

  雖然 AI 想改進，但：
  - 原本有效規則被刪掉
  - 新規則未經驗證
  - 整體表現可能變差
  這種現象稱為：Skill Drift、Prompt Drift。也就是技能逐漸偏離原本有效的內容。
  ```
- Bounded Text Updates 的做法
  ```
  SkillOpt 不允許：整份文件重寫
  而是限制：新增少量規則（Add）
  1. 收集錯誤訊息
  2. 查詢系統日誌
  + 3. 檢查最近變更
  4. 驗證修正結果

  修改單一規則（Replace）
  - 查詢系統日誌
  + 查詢最近24小時系統日誌

  刪除少量規則（Delete）
  - 永遠重新開機
  ```
- 可以把它想成文字版 Learning Rate
  ```
  在神經網路：Learning Rate = 每次權重更新幅度
  如果學習率太大：最佳解 ↓ 更新過頭 ↓ 震盪
  同樣地，在技能優化中：技能文件 ↓ 一次改太多 ↓ 品質下降
  ```
- Bounded Update
  ```
  AI只允許：- 搜尋至少兩個來源，僅修改一句話，風險低很多。
  ```
- 看法：
  ```
  參數 = 手冊
  梯度 = 報錯
  學習率 = 編輯預算
  ```

### Held-out Selection Gate（保留驗證選擇閘門）
> Held-out Selection Gate（保留驗證選擇閘門） 是 SkillOpt 論文中的核心機制之一，用來決定：AI 提出的技能修改（Skill Update）是否真的值得保留。它的概念其實和機器學習中的 Validation Set（驗證集） 非常相似。
> 總結：Held-out Selection Gate（保留驗證選擇閘門）就是 SkillOpt 用來審核技能更新的品質控制機制：只有當新技能在未參與訓練的 Held-out 驗證任務上表現更好時，修改才會被接受；否則直接捨棄。


# 機器學習
### Gradient（梯度）
> Gradient 是機器學習、深度學習與強化學習中最核心的概念之一。一句話來說：Gradient（梯度）告訴我們模型參數應該往哪個方向調整，才能讓誤差（Loss）下降得最快。
> 總結：Gradient（梯度）就是 Loss 對模型參數的變化率，指出「往哪個方向調整參數，才能最快降低誤差」。




# AI （人工智慧領域）
### Atomic Editing（原子級編輯）
> 原子級編輯（Atomic Editing） 是一種文件或程式碼修改方法，指的是：每次只做一個最小、明確、可驗證的修改動作。「原子（Atomic）」借用自物理學與資料庫術語，表示一個不可再分割的最小操作單位。

### 多模態之跨模態搜尋（Cross-Modal Search in Multimodal AI）
> 多模態之跨模態搜尋（Cross-Modal Search）是指利用一種模態（如文字、圖片、語音、影片）作為查詢，去搜尋另一種模態中的相關內容；其核心是將不同模態轉換到同一個向量空間（Embedding Space），讓 AI 能理解「同一概念的不同表現形式」，因此成為 Gemini、GPT、CLIP、NotebookLM 等現代多模態 AI 系統的重要基礎技術。
#### [多模态之跨模态搜索(05:04)](https://www.youtube.com/watch?v=YQtrSmxDIoM)
> 這段教學內容介紹了跨模態檢索的核心原理，解釋如何讓電腦學會用文字直接搜尋影像內容，而非依賴傳統的文件名對齊。由於文字與圖像的原始數據維度完全不同，技術關鍵在於利用神經網絡編碼器將兩者轉換，並映射至一個共同語義空間。在這個統一的座標系中，語義相似的文字向量與圖像向量會彼此靠近，使系統能透過計算餘弦相似度來衡量關聯性。最終，這種方法打破了媒介形式的限制，實現了根據語義相關性對搜尋結果進行精準排序的目標。
- 多模態之跨模態搜尋（Cross-Modal Search in Multimodal AI）
  多模態之跨模態搜尋（Cross-Modal Search in Multimodal AI） 是人工智慧中的一項重要技術，指：使用一種資料型態作為查詢（Query），去搜尋另一種資料型態中的相關內容。
  其中：
  - 模態（Modality）：資料的表現形式
    - 文字（Text）
    - 圖片（Image）
    - 語音（Audio）
    - 影片（Video）
    - 感測器資料（Sensor Data）
  - 跨模態（Cross-Modal）：
    - 查詢與搜尋目標屬於不同模態
- 為什麼能做到？
  核心技術叫：Shared Embedding Space（共享嵌入空間）。
  AI 無法直接比較：[ 文字 vs 圖片 ]因為格式不同。而是先轉成向量（Embedding）。於是兩者會出現在向量空間中相近的位置。
- 著名技術：
  - CLIP：OpenAI 的 CLIP 是最著名的跨模態模型之一。
  - Gemini：Google Gemini 屬於原生多模態模型。
  - GPT-4o / GPT-5 系列


# Deep Learning （深度學習領域）
### Cosine Decay（餘弦衰減）
> Cosine Decay（餘弦衰減） 是深度學習中常用的一種學習率（Learning Rate）調度策略，用來讓學習率隨著訓練過程平滑下降。簡單來說：一開始用較大的學習率快速學習，後期逐漸降低學習率，讓模型更穩定地收斂。



