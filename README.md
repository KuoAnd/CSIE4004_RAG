# RAG 語音檢索問答系統

本專案是一套結合 **語音輸入** 與 **RAG 檢索技術** 的智慧問答系統，使用者可透過語音上傳，系統會自動轉錄、嵌入並建立向量資料庫，最終由 Gemini API 回答使用者的問題。

---

## 快速開始

### 1. 前置準備

#### 啟用 Notebook

- 將本 Notebook 上傳至 [Google Colab](https://colab.research.google.com) （建議但非必要）

#### 填入 API 金鑰

- 在 `Environment` 區段填入你的 `GEMINI_API`：
  ```python
  GEMINI_API = "YOUR_GEMINI_API_KEY"
  ```
- 若尚未申請金鑰，請參考官方文件：[Gemini API 金鑰教學](https://ai.google.dev/gemini-api/docs?hl=zh-tw)

#### 設定資料夾路徑

請手動設定以下變數：

1. `save_folder`: 儲存錄音與文字資料的資料夾
2. `font_path`: 用來顯示Word Cloud的字體路徑

 你可以預先將 MP3 檔放進 `audio_folder`，或稍後使用介面即時上傳

#### 上傳字體

請將一款支援繁體中文的字體（如 `NotoSansCJK-Regular.ttc`，見附件）上傳至你設定的 `font_path`。

---

### 2. Notebook 執行流程

1. **安裝套件**

   執行第一個 Cell，自動安裝所有所需套件  
   遇到要求重新啟動工作階段的提示時，**請忽略，點選取消**

2. **依序執行 Cell**

   無需修改程式碼，按順序執行每個區塊即可。

3. **啟動互動介面**

   在最後一個 Cell 中會輸出類似以下內容：

   ```
   Colab notebook detected. This cell will run indefinitely so that you can see errors and logs. To turn off, set debug=False in launch().
   * Running on public URL: https://XXXXX.gradio.live
   ```

   點擊該網址即可開啟 Gradio 介面進行語音上傳與問答互動。

---

## 系統簡介

本系統包含以下核心流程：

1. **語音轉文字**：使用語音識別技術將 MP3 轉為逐字稿  
2. **向量化嵌入**：使用語意模型將文字轉為向量，並儲存於 FAISS 資料庫  
3. **RAG 檢索強化**：根據提問檢索相關段落，交由 Gemini 回答

---

## Demo 展示

[功能示範影片](https://www.youtube.com/watch?v=YX8PeTnjxFg)
