# Google Map Collection Operation Handbook

## 核心邏輯：先檢查，後操作

為了防止錯誤移除已有的書籤，所有 Agent 在操作 Google Map Collection 時必須遵循以下 SOP：

1. **搜尋地點**：輸入全名或精確地址。
2. **狀態檢查 (CRITICAL)**：獲取 Snapshot 並檢查該地點的按鈕文字：
   - 如果按鈕顯示 **「已儲存 (Saved)」** 且清單包含 **「Osaka 2026」**：
     - **絕對禁止再次點擊**。
     - 直接跳過，更新 Checklist 為 ✅。
   - 如果按鈕顯示 **「儲存 (Save)」**：
     - 點擊「儲存」。
     - 在彈出的清單中選取 「Osaka 2026」。
     - 再次獲取 Snapshot 確保按鈕狀態變為「已儲存」。
3. **防止重複搜尋**：在每次新搜尋前，必須確保 Search Bar 已清空，避免 URL 跳轉錯誤。
4. **連鎖店處理**：
   - 必須標記至少兩間分店（如：大阪一間、京都一間）。
   - 每間分店都必須獨立執行上述檢查邏輯。

## 常見錯誤預警
- **雙擊取消**：在「已儲存」狀態下再次點擊會導致地點從清單中移除。
- **URL 滯後**：搜尋後未等待頁面加載完成就點擊，會導致標記錯誤的地點。

Recorded by Charlotte (Directly supervised by Jam)
