# EBMT 網站交接給 Gemini

## 先讀這份

這是目前已部署版本 12 的可攜式原始碼快照。來源 commit：`1c1977f36cba183249d6d69b23b8ca66e51e358c`。
原網站：https://ebmt-transplant-study-zh-2026.adeption.chatgpt.site/
原 Sites project ID：`appgprj_6af201876a288191a5f121c772c0f8a1`。

## 執行網站

這是沒有建置步驟的靜態 HTML/CSS/JavaScript 網站。解壓後於專案根目錄執行：

```sh
python3 -m http.server 8000 --directory dist
```

開啟 http://localhost:8000/ 。請透過 HTTP 伺服器開啟，因為網站會 fetch JSON；直接點兩下 index.html 可能失敗。

## 主要檔案

- `dist/index.html`、`dist/style.css`：頁面與樣式。
- `dist/app.js`：章節、搜尋、測驗、筆記、書籤、進度與備份。
- `dist/translation.js`：逐段中英對照、閱讀模式、頁面篩選與章內搜尋。
- `dist/book.json`：94 章目錄、摘要、原文索引、章節起迄與小節。
- `dist/chapters/00.pdf`：書前內容；`01.pdf` 至 `94.pdf`：原始章節 PDF。
- `dist/translations/index.json`：翻譯進度的權威索引。
- `dist/translations/NN.json`：已發布譯文。
- `README.md`：歷次工作紀錄；其中歷史性的進度或限制以最新索引為準。
- `.openai/hosting.json`：原 Sites 專案識別與靜態目錄設定，不含發布授權。

## 目前進度與必須重新核對的品質問題

索引標示完成 25/94 章：1、6、72–94；213 頁、1,415 組文字。其餘 69 章與 41 頁書前內容為待譯。一般續作順序為 71、70、69……，每輪最多兩章。

注意：索引的「完成」是既有發布狀態，不能視為已符合逐段全文品質要求。第 72、73 章目前每頁只合成一個中英區塊；中文部分有濃縮段落與未逐列完整重現的表格，英文抽文也仍有雙欄混排。因此這兩章需要優先逐段重新對照 PDF、補全表格並重建中英配對；不能直接把它們當作完整全文範本。先前章節也應抽查全文涵蓋度，不能只以頁數、數字 token 或索引狀態判定完成。保留既有成果，修正時記錄差異。

## 翻譯要求

直接依 PDF 全文逐段翻成繁體中文，不以摘要替代。保留小節、每段英中對照、表格所有列與欄、圖說及文字標籤、來源頁碼。藥名與專有名詞可英文；完整英文書目與 Google/Scholar 連結保留。跨頁段落可合併，須記錄起迄來源頁碼。逐頁視覺檢查雙欄順序、否定句、數字、劑量、單位、上下標與不等號。不要使用舊 Google 機翻快取。持續顯示「AI 翻譯，未經人工專科校訂」及未完成狀態。

原頁連結使用 `book.json` 的 `start` 座標，章內 PDF 頁碼為 `來源頁碼 - chapter.start + 1`。PDF 印刷頁碼與網站來源座標不同，切勿直接採用頁腳印刷數字。第 72 章座標 642–650，第 73 章 651–659。

## 資料格式

沿用現有 JSON 結構，包含 id、title、engine、review、status、scope、paragraphs，以及 pages[].page、pages[].blocks[]。每個 block 要有唯一 id、page、en、zh、review，可另有 endPage、note、links、retained。`paragraphs` 必須等於實際 block 數。完成後同步 index 的 completedChapters、chapters、pages、paragraphs；不要提前標記未驗證章節。

## 個人資料與部署

筆記、書籤、已讀與測驗自評存於使用者瀏覽器的 localStorage（key：`ebmt-study-v1`），不在此 ZIP 裡。搬家前請在原站「我的複習」→「匯出備份」，於新站再「匯入備份」。不同網域不會自動沿用 localStorage。

原站目前只允許擁有者存取。此靜態原始碼不包含 Sites 平台登入／存取控制；部署到別的平台時，必須另行設定私人存取。Gemini 不會因拿到 ZIP 就取得原站部署權。原 Sites 上更新需有原專案授權；也可先本機修改後交回使用者。不要把網站直接公開。

原有自動續譯任務在打包時仍啟用；此匯出未變更它。交接前應協調是否暫停，避免兩方同時更新。ZIP 只代表這個版本的快照。

## 驗證與授權

修改後檢查 JS 語法、JSON、段落唯一性、所有原頁連結、全文搜尋、閱讀模式、未翻譯標示、筆記／書籤／備份還原。內容驗證需逐段對照原 PDF，而非只測畫面能否載入。

原書為 The EBMT Handbook (2024)，保留原作者、DOI、CC BY 4.0 與第三方圖像註記。網站不是 EBMT 官方譯本。PDF 的各別圖表可能有不同權利註記，延續使用時須遵守原標示。

## 可直接貼給 Gemini 的開工指示

請解壓並先讀 GEMINI_HANDOFF.md、README.md、dist/translations/index.json。先跑起 dist 靜態網站並確認現有功能。先修訂 72、73 章的逐段全文涵蓋與表格完整性，再依倒序處理尚未完成章節，每批最多兩章。以 dist/chapters 原始 PDF 為唯一翻譯來源，逐頁視覺核對雙欄、數字、否定與上下標。保留原有資料格式、私人存取需求及筆記書籤備份功能，只把完整驗證的章節標為完成。
