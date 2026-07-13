# ChatGPT

## 教學資源：
### YouTub：
- [ChatGPT 和 Codex 合体！「Add to Task」才是最大更新 | GPT5.6深度解读(22:56)](https://www.youtube.com/watch?v=mJEIjgiffjc)
- [wow](https://www.youtube.com/@wow.insight)
  - [解析 UNC/CMU/Stanford 等联合力作：如何打造靠谱的科研 Agent(19:20)](https://www.youtube.com/watch?v=FPe5wRlIdMU)
- [灵姐说AI  |  Ling Talk AI](https://www.youtube.com/@aihublab)
  - [GPT Live 实测：全双工语音，真人感到底有多强？｜ PK 豆包/同传/面试/脑暴/辩论/喜剧｜ Open AI(35:29)](https://www.youtube.com/watch?v=-hnd202HYZs)

## Codex
> Codex 可以：
> - 自動整理 PDF：幫我閱讀這 20 篇論文
> - 擷取重點：分析 What、How、Why、找出研究缺口
> - 建立 Markdown、建立 Word、建立 PowerPoint
> - 更新你的文獻資料夾
### 教學資源
- [Codex保姆級完整教學：從入門到進階，自動生成內容、網頁、影片和App，快速學會指揮你的超級AI Agent(29:54)](https://www.youtube.com/watch?v=tfeCwDT-5m0)


### 教學範例
#### Ex:[一個 AI 助手打趴整套 Office 軟體！超強 Codex 從表格簡報、合併列印、架設網站全部一手包辦！(19:49)](https://www.youtube.com/watch?v=W5ymBPi53Tw)
  > 校園園遊會為例：
  > 這段教學影片詳細介紹了 OpenAI 推出的 AI 助理 Codex，強調其具備超越一般對話型 AI 的執行力，能直接操作電腦檔案並自動化處理繁瑣任務。 

#### Ex:[寫提示詞太累，而且工作流程很難交待清楚？Codex 讓你直接「做給 AI 看」，徹底終結這個困境！(05:26)](https://www.youtube.com/watch?v=SFWYaF0HJiw)
> 這段教學介紹了 OpenAI 為 Codex 推出的 Record & Replay（錄製與重播） 功能，
> 旨在解決過往需撰寫複雜提示詞才能交代自動化流程的痛點。用戶現在只需透過實際操作電腦畫面示範一次任務，AI 便能將動作分析並儲存為具備邏輯步驟的 Skill（技能） 檔案。未來遇到相同需求時，Codex 即可根據這項技能進行自動化操作，甚至能優先以程式腳本執行以確保處理過程既快速又穩定。這項創新大幅簡化了跨應用程式的雜務處理，讓使用者能以直覺的視覺學習取代繁瑣的文字指令，輕鬆管理數位工作流程。
- 安裝 Codex
- 使用 ChatGPT 帳號登入 |> 設定 |> Computer use |> 開啟 {任何應用程式 | Google Chrome} 功能
- 外掛程式 {新增外掛程式} |> Record
  - [對話]輸入指令：{@Record} 就可以看到這個外掛程式。 => 按下 [Tab] 鍵將它載入進來。 => 再按下 [Enter] 鍵後，Codex就會顯示這個外掛已經啟用。
  - [對話]輸入指令：{開始錄製} 就可以開始使用這項功能。
- 測試：想要把 Gmail 收到的收據，全部登記到 Google 試算表
  - 將 Gmail 信件中的收據中 [公司的名稱]、[金額] 先反白起來 按下 Command +C 進行複製-> 貼上在 Google 試算表對應欄位上 => 操作完畢後就在底部點繫 [結束錄製] => 此時 Codex 就會開始分析剛才我們錄製的內容，並且把整個流程儲存成一個 Skill(技能)檔案。此時 Codex 回饋說明，以後把 Gmail 的收據登記到 Google 試算表時，就會觸發這一項技能。實際上 Codex 是一個用來記錄操作流程的文字檔
  - 如果要檢視剛才的 Skill(技能)，只要點繫 {外掛程式 > 技能標籤} 就能顯示我們剛才錄製好的技能。





## GPT-5.6 模型家族
Sol、Terra、Luna 是 GPT-5.6 模型家族的三個不同層級，它們並不是三個完全不同的 AI，而是針對能力、速度、成本做了不同的最佳化。最簡單的理解方式是：
- ☀️ Sol（太陽）：能力最強
  > 解決最難的編碼、研究、知識工作和高風險專業任務。
- 🌍 Terra（地球）：最均衡
  > 適合日常專業工作的一層。
- 🌙 Luna（月亮）：最快、最省資源
  > 則瞄準高頻、大規模、對成本和速度極度敏感的任務。

官方 API 定價也反映了這種定位：Sol 成本最高、Terra 居中、Luna 最低。
| 項目     | ☀️ Sol          | 🌍 Terra   | 🌙 Luna    |
| ------ | --------------- | ---------- | ---------- |
| 定位     | 旗艦模型            | 均衡模型       | 輕量高速模型     |
| 推理能力   | ⭐⭐⭐⭐⭐           | ⭐⭐⭐⭐☆      | ⭐⭐⭐☆☆      |
| 回應速度   | 較慢              | 中等         | 最快         |
| 成本/API | 最高              | 中等         | 最低         |
| 適合工作   | 複雜研究、程式開發、Agent | 日常工作、寫作、分析 | 快速問答、摘要、分類 |


