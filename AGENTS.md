# AGENTS.md - Anita Li 個人作品集與 Side Project 展示站開發規範

> 本文件是本專案的「AI 開發與協作手冊（AI Agent Guidelines）」。當任何 AI 助手（包括 Claude、ChatGPT、Gemini、Cursor、Copilot 等）接手本專案時，**必須首先完整閱讀並嚴格遵守本文件規定的所有架構、命名、樣式與擴充規則**，以確保專案能一致、高效且無痛地擴展。

---

## 1. 專案願景與目的 (Project Purpose)

* **專案名稱**：Anita Li - Personal Portfolio & Side Project Showcase
* **專案定位**：聚焦於 **Agentic AI、雲端架構（AWS / Serverless）、全端重構及多模態資料分析** 的現代化個人專業作品集。
* **主要受眾**：技術招募人員（Tech Recruiters）、工程主管（Engineering Managers）、技術同儕與協作者。
* **社交與聯絡主頁**：LinkedIn [`https://www.linkedin.com/in/llh26`](https://www.linkedin.com/in/llh26) • Email `anita.tw88@gmail.com`。
* **核心目標**：
  1. 具體展現 Anita 在大規模專案重構、AI 代理工作流、雲端推薦系統與機器學習競賽的實戰亮點。
  2. 建立標準化、低耦合、高可維護性的純前端架構，讓 AI 可以在 1 分鐘內依標準 SOP 新增或修改專案頁面。

---

## 2. 技術棧與依賴規範 (Tech Stack)

為了保證 GitHub Pages 零建置環境（Zero-build）、最快部署速度與最高相容性，本專案嚴禁使用需要本機打包編譯的複雜框架（如 Webpack、Vite、Node.js Build）：

* **核心技術**：語意化 HTML5 + 原生 JavaScript (ES6+ Vanilla JS)。
* **樣式框架**：**Tailwind CSS (CDN)**
  * 引入方式：`<script src="https://cdn.tailwindcss.com"></script>`
  * 配置方式：於各頁面 `<head>` 中配置 `tailwind.config`，統一全站色系、陰影標準與 **`darkMode: 'class'`**。
* **主題系統**：原生純 JS 雙色主題（亮色 / 暗色切換，支援 `localStorage` 記憶與系統偏好偵測）。
* **互動功能組件**：
  * 手機版漢堡選單抽屜 (Mobile Hamburger Menu Drawer)。
  * 懸浮平滑返回頂部按鈕 (Floating Scroll-to-Top Button，滾動超過 300px 自動浮現)。
* **圖標庫**：**Font Awesome 6 (CDN)** 或精簡語意化 SVG
  * 引入方式：`<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">`
* **部署平台**：GitHub Pages（以 `main` 分支根目錄直接發布）。

---

## 3. 檔案目錄結構與命名規範 (File Structure & Naming)

```text
my-portfolio/
├── AGENTS.md                  # [重要] 本檔案：AI 專案開發規範手冊
├── README.md                  # GitHub 專案介紹、展示截圖與部署教學
├── index.html                 # 網站首頁：個人介紹、分類過濾器、專案卡片牆、雙主題切換、手機選單
├── projects/                  # 專案獨立詳情頁目錄
│   ├── template.html          # [標準範本] AI 新增專案時必須複製此範本（支援雙主題與回頂按鈕）
│   ├── 01-agentic-modernization.html   # 專案 1：台積電實習 Agentic AI 全端重構
│   ├── 02-aws-restaurant-rec.html       # 專案 2：AWS Bedrock 個人化智慧餐廳推薦系統
│   ├── 03-adam-multimodal-analytics.html# 專案 3：ADAM 服務業滿意度多模態分析系統
│   └── 04-trade-timeseries-forecasting.html # 專案 4：航港大數據兩岸貿易時間序列預測
└── assets/                    # 靜態資源目錄
    ├── images/                # 專案截圖、架構圖、個人頭貼
    └── documents/             # 相關簡報、報告或文件
```

### 檔案命名硬性規則
1. **目錄全小寫**：所有目錄名稱均為全小寫英文（例如 `projects/`, `assets/`）。
2. **專案頁面命名格式**：`projects/{編號}-{kebab-case-slug}.html`
   * 編號為兩位數：`01`, `02`, `03`...
   * Slug 必須為有意義的英文短詞，以連字符 `-` 分隔。
   * 範例：`projects/05-smart-chatbot.html`。
3. **禁止中文或空格檔名**：所有 HTML、圖片與資源檔案名稱絕對不得包含中文字元或空白鍵。

---

## 4. 設計系統與雙色主題規範 (Design System & Dual Themes)

全站採用 **現代極簡科技風格（Modern Clean Tech & Slate Theme）**，全面支援 **亮色（Light Mode）** 與 **暗色（Dark Mode）** 即時切換，並保證在兩種模式下皆具備清晰的文字對比度與流暢過渡。

### 4.1 雙色主題配色方案 (Light & Dark Modes)

| 介面元素 | 亮色模式 (Light Mode) | 暗色模式 (Dark Mode) |
| :--- | :--- | :--- |
| **頁面背景** | `bg-slate-50` | `dark:bg-slate-900` |
| **導覽列背景** | `bg-white/90 border-slate-200` | `dark:bg-slate-900/90 dark:border-slate-800` |
| **主要文字標題** | `text-slate-900` | `dark:text-white` |
| **次要內文字體** | `text-slate-600` | `dark:text-slate-300` |
| **標註與輔助文字** | `text-slate-500` | `dark:text-slate-400` |
| **主要卡片背景** | `bg-white border-slate-200 shadow-sm` | `dark:bg-slate-800/80 dark:border-slate-700/60 dark:shadow-xl` |
| **卡片內部區塊** | `bg-slate-50 border-slate-200` | `dark:bg-slate-900/70 dark:border-slate-700/60` |
| **技術標籤膠囊** | `bg-slate-100 text-slate-700` | `dark:bg-slate-700/60 dark:text-slate-200` |

### 4.2 專案類別標籤色（Category Badges）
新增專案時，必須嚴格依照其分類使用對應的 Tailwind 雙色模式標籤樣式：

| 領域分類 (Category) | Badge 雙色樣式代碼 (Tailwind Class) | 適用專案類型 |
| :--- | :--- | :--- |
| **Agentic AI** | `bg-purple-50 dark:bg-purple-500/10 text-purple-700 dark:text-purple-400 border border-purple-200 dark:border-purple-500/20` | AI Agent、Workflow 自動化、LLM 協作 |
| **Cloud & Architecture** | `bg-blue-50 dark:bg-blue-500/10 text-blue-700 dark:text-blue-400 border border-blue-200 dark:border-blue-500/20` | AWS、Serverless、微服務、雲端部署 |
| **Multimodal AI** | `bg-emerald-50 dark:bg-emerald-500/10 text-emerald-700 dark:text-emerald-400 border border-emerald-200 dark:border-emerald-500/20` | 語音/圖像/文本多模態、情緒辨識、新創系統 |
| **Data Analytics** | `bg-amber-50 dark:bg-amber-500/10 text-amber-700 dark:text-amber-400 border border-amber-200 dark:border-amber-500/20` | 時間序列、商業智慧、資料探勘、競賽數據分析 |
| **Full-Stack & Web** | `bg-cyan-50 dark:bg-cyan-500/10 text-cyan-700 dark:text-cyan-400 border border-cyan-200 dark:border-cyan-500/20` | 前端開發、Spring Boot、Next.js、全端應用 |

---

## 5. 專案詳情頁內容結構規範 (Project Page Structure)

每個獨立專案頁面必須嚴格依照 `projects/template.html` 的結構組織，章節順序不得隨意變更：

1. **頂部導覽列 (Top Navigation)**：包含「返回首頁 (Back to Home)」按鈕、LinkedIn 捷徑、主題切換按鈕與聯絡按鈕。
2. **專案 Hero 區塊**：
   * 類別標籤（Badge）+ 發表年份
   * 專案正式名稱（大標題）
   * 一句話核心亮點定位（Subheadline）
   * 核心成果數據列（KPI Summary Row，例如：效率提升 75%、人為介入降至 30%）
3. **專案規格摘要表（Sidebar / Quick Info Card）**：
   * 擔任角色 (My Role)
   * 專案時程 (Timeline)
   * 合作單位 / 專案性質 (Affiliation)
   * 技術堆疊標籤 (Tech Stack Tags)
   * 專案連結（GitHub / Demo / 論文 / 簡報）
4. **專案詳細內容章節（Main Content Sections）**：
   * **章節一：背景與痛點 (Problem Statement & Context)**
   * **章節二：系統架構與技術方案 (System Architecture & Tech Solution)**
   * **章節三：關鍵亮點與功能特色 (Key Features & Engineering Highlights)**
   * **章節四：具體成效與數據驗證 (Impact, Metrics & Awards)**
   5. **懸浮組件**：右下角平滑返回頂部按鈕。
6. **底部翻頁導覽 (Next/Previous Project Links) & Footer**。

---

## 6. AI 擴充與修改 SOP（AI Step-by-Step Workflow）

當使用者要求 AI：**「幫我新增一個專案」** 或 **「修改現有專案」** 時，AI **必須按以下 3 個步驟執行**：

### 步驟 1：建立專案詳情頁
1. 讀取 `projects/template.html` 作為基底。
2. 計算下一個專案序號（例如已存在 04，則新專案為 `05`）。
3. 產生檔名：`projects/{編號}-{專案名稱縮寫}.html`。
4. 將專案內容按第 5 節標準結構填入，確保所有 Tailwind Class 同時定義亮色與 `dark:` 暗色樣式。

### 步驟 2：在首頁 `index.html` 註冊專案卡片
1. 開啟 `index.html`，尋找 `<div id="projects-grid" ...>` 區塊。
2. 複製「7.1 標準卡片 HTML 代碼範本」，填入新專案的標題、摘要、指標與標籤。
3. 確保 `data-category` 屬性正確（用於篩選按鈕過濾，如 `agentic-ai`, `cloud`, `multimodal`, `data`, `web`）。
4. 檢查首頁頂部的「精選專案數量統計（KPI）」是否需要加 1。

### 步驟 3：防呆檢查（Self-Verification Checklist）
* [ ] 檔案路徑與命名是否完全符合規範？
* [ ] 元素是否同時具備亮色與暗色 (`dark:...`) 樣式？
* [ ] `index.html` 卡片的 `<a href="projects/...">` 連結是否能正確跳轉？
* [ ] 專案詳情頁中的「返回首頁」連結是否為 `../index.html`？
* [ ] 點擊主題切換按鈕，新頁面的背景與文字顏色是否能正常切換且文字清晰？
* [ ] 手機版瀏覽時，漢堡選單展開與關閉是否流暢？
* [ ] 是否沒有使用任何未宣告的外部依賴，全站可在 GitHub Pages 直接免編譯執行？

---

## 7. AI 一鍵驗證測試 Prompt 範例 (Verification Prompts)

審查者或使用者可以直接將以下 Prompt 餵給任何 AI 助手，以驗證 AI 是否能完全依照本規範自動完成新功能擴充：

```markdown
【測試任務】：
請閱讀本專案的 AGENTS.md 規範手冊，幫我新增一個專案：
- 專案名稱：智慧會議摘要與任務萃取機器人 (Smart Meeting Summarizer)
- 分類：Agentic AI
- 技術棧：Python, Whisper, Claude API, FastAPI, Celery
- 成果指標：會議記錄產出時間節省 80%、關鍵 Action Items 萃取準確率 94%
請依照 AGENTS.md 規範執行：
1. 複製 projects/template.html 建立 projects/05-meeting-summarizer.html 並填入完整章節。
2. 在 index.html 的 projects-grid 區塊加入對應的雙色卡片組件，並設定正確的 data-category。
3. 依照防呆檢查清單驗證所有路徑與樣式。
```

---

## 8. AI 執行約束與嚴格禁止事項 (Strict Prohibitions)

1. **嚴禁破壞無編譯架構**：絕對不要在任何頁面中引入需要 npm 建置、Node 服務或本機編譯的工具。
2. **嚴禁遺漏雙色樣式**：編寫 HTML 時，所有顏色相關 Class 必須成對提供（例如設置了文字顏色，必須同時宣告亮色類別與 `dark:` 類別）。
3. **嚴禁使用生硬假資料**：新增或修改專案內容時，必須基於真實工程實踐或簡報資訊，保留專業細節與可量化指標。
4. **嚴禁絕對本機路徑**：全站所有 CSS、JS、圖片與超連結一律使用相對路徑（例如 `projects/...` 或 `../index.html`）。
5. **保持代碼自洽與自註解**：每次修改均需維持乾淨的 HTML 縮排，並保留關鍵註解，方便使用者與後續接手之 AI 閱讀。
