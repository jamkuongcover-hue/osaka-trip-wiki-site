# 大阪及關西旅遊規劃 README

## 核心準則 (Charlotte's Protocol)
**重要：每次進行任何關於大阪之旅 (Osaka Trip) 的任務前，Charlotte 必須先閱讀本 README 檔案。**
1. **完成匯報**：每次完成任何地點的更新或研究後，必須即時在 BlueBubbles 頻道向 Jam 匯報進度，嚴禁「不告而別」。
2. **全繁體化**：所有文件（標題、內容、目錄）必須優先顯示繁體中文名稱，確保 Jam 閱讀流暢。
3. **持續維護**：隨著 Jam 的新要求增加，隨時更新本 README。

## 1. 檔案命名規範
為確保 Obsidian 關係圖 (Graph View) 清晰且避免檔名衝突，禁止使用如 `catalog.md` 或 `plan.md` 等通用名稱。
- **目錄檔案**：必須包含地區與類別，格式為 `[地區]-[類別]-catalog.md` (例如：`osaka-restaurants-catalog.md`)。
- **計畫檔案**：使用 `osaka-trip-plan.md`。
- **命名規範**：地點標題必須包含「中文名稱 (英文名稱)」，例如 `# 三嶋亭 (Mishimatei)`。
- **目錄清單**：所有目錄檔案 (`catalog.md`) 必須同時列出中文及英文名稱，確保可讀性。
- **內容語言**：主要內容、Charlotte 的貼士及地點描述必須使用繁體中文。

## 2. 關係圖優化 (Obsidian Graph Mode)
- **連結方式**：所有檔案互連必須使用 `[[檔案名稱]]` 格式。
- **層級連結**：每個具體地點檔案應連結回其所屬的地區目錄。
- **跨區連結**：若有相關行程，請主動建立連結。

## 3. 視覺化研究與匯報規範 (Visual & Reporting Protocol)
- **資產先行**：在進行 `web_search` 或下載圖片前，**必須先檢查 `memory/osaka-trip/assets/` 資料夾**，確保不會重複下載已存在的圖片。
- **即時圖文匯報**：當 Jam 詢問地點資訊時，若本地已有相關圖片，**必須使用 `message(action="sendAttachment")` 直接發送圖片**，嚴禁只發送 `![[filename]]` 文本。
- **場景還原**：使用 `Web-Enhanced Reference Protocol` 搜尋並下載真實地點圖片。
- **嚴禁截圖**：禁止直接使用網頁截圖作為展示。必須透過瀏覽器解析 HTML，找出原始圖片 URL 並直接下載原始檔案。
- **資產管理**：下載後的原始圖片必須存放在 `memory/osaka-trip/assets/` 對應的地區資料夾內。
- **檔案嵌入**：將圖片以 `![[圖片名稱]]` 格式嵌入至具體地點的 `.md` 檔案中，並在下方配以 Charlotte 的風格描述。

## 4. 內容標準
- 優先參考香港人常用旅遊資訊（Flyday, U Travel, Klook 等）。
- 每個地點必須包含：地址、營業時間、特色、及 Charlotte 的「毒舌/貼心」貼士。
- 大阪目標：30+ 景點、20+ 餐廳。

## 5. 權限與協作協定 (Governance Protocol)
**本目錄 (`memory/osaka-trip/`) 採用 Single-Writer 協定：**
1. **唯一寫入者**：僅限 `osaka-trip-manager` subagent 擁有本目錄下所有檔案的編輯權限。
2. **唯讀權限**：其他所有角色（包括 Main Agent, 其他 Researchers 或 subagents）均為唯讀 (READ-ONLY) 權限。
3. **委託機制**：任何針對本目錄的編輯請求，必須委託 (delegate) 給 `osaka-trip-manager` 執行。
4. **工作日誌 (Working Log)**：每次編輯會話必須在 `working-log.md` 中記錄。每一次編輯必須記錄所有被修改檔案的精確完整路徑 (EXACT full path of EVERY individual file modified)。嚴格禁止使用萬用字元 (例如 *.md) 記錄修改內容。僅在進行大規模的「唯讀審計 (READ-ONLY audits)」且絕對必要時才允許使用萬用字元，但對於所有寫入操作，必須優先列出具體檔名。

## 6. 版本控制 & 網站同步 (Git & Wiki Sync)
- **提交規則**：每次任務完成後，必須進行 `git commit` 並配以描述性提交訊息 (commit message)。
- **原始碼同步**：必須執行 `git push origin main` 將變更同步至 GitHub 原始碼倉庫。
- **網站發布 (CRITICAL)**：每次更新後，**必須** 執行以下步驟更新 Wiki 網站：
    1. 進入 `/Users/jamdow/.openclaw/workspace/quartz-site` 目錄。
    2. 執行 `npx quartz build` 重新構建網站。
    3. 進入 `public` 目錄，執行 `git add .`、`git commit -m "Deploy update"` 及 `git push origin main --force`。
- **審計路徑**：工作日誌 (Working Log) 仍為主要的「人類可讀」摘要，但 Git 提供最精細的審計追蹤 (audit trail)。

## 更新日誌
- 2026-02-27: 初始化 Git 版本控制系統，新增「版本控制」協定。
- 2026-02-26: 重組檔案結構，確立命名規範，新增「資產先行」與「即時圖文匯報」協定。
