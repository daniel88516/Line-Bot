# Line Bot

此 repository 收錄 LINE Bot 的開發練習與本機測試流程，包含 Bot 專案、ngrok webhook 測試設定，以及資料處理相關檔案。專案目標是了解聊天機器人如何接收 LINE 平台事件，並回覆使用者訊息。

## 技術實作

- **Webhook 架構**：LINE 平台將使用者事件送至伺服器端 webhook，應用程式依事件內容執行對應的訊息處理與回覆流程。
- **本機公開測試**：透過 ngrok 將本機服務暫時對外公開，使 LINE Developers Console 能連到開發中的 webhook URL，方便不部署正式伺服器時進行測試。
- **模組分工**：`LineBot_gunico/` 放置 Bot 專案，`LineBot_ngrok/` 收錄 ngrok 測試內容，`資料處理/` 保存 Bot 使用的資料整理或處理檔案。
- **憑證管理**：LINE Messaging API 的 Channel Access Token 與 Channel Secret 應以環境變數或本機設定檔保存，不能提交到公開 repository。

## 使用方式

1. 建立 LINE Messaging API Channel，取得 Channel Secret 與 Access Token。
2. 在本機設定 Bot 所需憑證並啟動服務。
3. 以 ngrok 建立公開 HTTPS URL，填入 LINE Developers Console 的 webhook 設定。
4. 將 webhook 驗證成功後，即可從 LINE 測試訊息事件與回覆流程。
