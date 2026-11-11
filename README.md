# Anita Li - 個人作品集與 Side Project 展示站 (Personal Portfolio)

> 本專案為 Generative AI 實戰作業成果：設計一個具備完整 `AGENTS.md` 開發規範的個人作品集與 Side Project 展示站，讓 AI 能準確理解專案架構並以高度一致的規範快速擴充新內容。

---

## 📌 作業繳交資訊 (Submission Information)

1. **專案簡介**：
   本專案是李舲熏（Anita Li）的個人專業作品集網站，採用純 HTML5 + Tailwind CSS (CDN) 打造現代極簡卡片式架構，全面支援**亮色 / 暗色雙主題切換、手機版漢堡選單與平滑回頂功能**。網站收錄了 4 個不同面向的實踐專案：包含台積電 IT 實習的 **Agentic AI 全端現代化重構**、**AWS Serverless 個人化智慧餐廳推薦系統**、**ADAM 多模態服務業滿意度分析系統**（臺灣數創大賞銀獎）、以及**兩岸航線貿易時間序列預測**（航港大數據競賽佳作）。專案核心亮點在於制定了工業級的 `AGENTS.md`，使任何大語言模型皆能依據 SOP，在 1 分鐘內無痛擴充新專案頁面與首頁展示卡片。
2. **GitHub Repository 連結**：`https://github.com/anita-tw88/my-portfolio` *(請於上傳後替換為您的實際 Repo 網址)*
3. **網頁瀏覽連結 (GitHub Pages)**：`https://anita-tw88.github.io/my-portfolio/` *(請於開啟 Pages 後替換為您的實際網址)*
4. **核心規範文件**：請參閱根目錄下的 [`AGENTS.md`](AGENTS.md)
5. **個人專業連結**：
   * LinkedIn: [https://www.linkedin.com/in/llh26](https://www.linkedin.com/in/llh26)
   * Email: `anita.tw88@gmail.com`
6. **簡短說明（AI 擴充機制與規則助益）**：
   * **標準化元件規格與雙色系統**：`AGENTS.md` 定義了首頁卡片組件的 Tailwind Class 與結構標準，並提供了各領域標籤（如 Agentic AI 為紫色、Cloud 為藍色、Multimodal 為綠色、Data 為橘色）在亮色與暗色模式下的對照色彩表，避免 AI 在產生卡片時發生視覺割裂或破版。
   * **模板驅動與防呆檢查**：規範所有新增專案必須複製 `projects/template.html` 進行填空，章節順序（背景、架構、亮點、成效）受到強制約束，確保每一頁皆維持高品質工程敘事。
   * **明確的 3 步驟 SOP 與驗證指令**：AI 接獲指令後，只需執行「1. 複製並命名詳情頁 -> 2. 在 index.html 的 Grid 區塊掛載標準卡片並設定 data-category 屬性 -> 3. 執行路徑、漢堡選單、主題切換與相對連結防呆查驗」，即可百分之百保證新頁面相容且可正常跳轉與篩選。`AGENTS.md` 第 7 節更附帶一鍵測試 Prompt 供審查者驗證。

---

## 🚀 專案目錄結構 (Project Directory)

```text
my-portfolio/
├── AGENTS.md                  # [核心文件] 給 AI 的專案規格手冊與擴充 SOP
├── README.md                  # 本檔案：專案簡介與部署說明
├── index.html                 # 網站首頁：個人介紹、分類過濾、專案卡片 Grid、雙主題、手機導覽
├── projects/                  # 獨立專案技術報告目錄
│   ├── template.html          # [標準範本] AI 新增頁面專用範本（支援雙主題與回頂）
│   ├── 01-agentic-modernization.html   # 專案 1：台積電 Agentic AI 全端重構
│   ├── 02-aws-restaurant-rec.html       # 專案 2：AWS Bedrock 智慧餐廳推薦系統
│   ├── 03-adam-multimodal-analytics.html# 專案 3：ADAM 服務業滿意度多模態分析
│   └── 04-trade-timeseries-forecasting.html # 專案 4：航港兩岸貿易時間序列分析
└── assets/                    # 靜態圖片、簡報與圖標資源
```

---

## 🛠️ 技術棧與架構特色 (Tech Stack)

* **零建置門檻 (Zero-Build)**：純原生 HTML5 + Vanilla JS，免除 Node.js、Vite 或 Webpack 編譯流程，推上 GitHub 即可秒速透過 GitHub Pages 上線。
* **雙色主題切換 (Dual Theme)**：內建亮色（極簡 Slate 白）與暗色（科技深藍）切換按鈕，支援 `localStorage` 記憶與系統主題偏好自動偵測。
* **行動端適配 (Mobile First)**：具備響應式排版與手機版專屬漢堡下拉選單。
* **懸浮平滑回頂 (Smooth Scroll-to-Top)**：滾動超過 300px 自動浮現，大幅優化長頁面閱讀體驗。
* **原生分類過濾器 (Vanilla Filter)**：以輕量 JavaScript 實現點擊標籤即時切換卡片顯示，無任何龐大第三方依賴。

---

## 📦 如何部署至 GitHub Pages（超簡單 2 種方式）

### 方式 A：GitHub 網頁拖曳上傳（推薦，無須終端機）
1. 在 GitHub 建立一個名為 `my-portfolio` 的全新 Public Repository。
2. 點擊網頁中央的 **"uploading an existing file"**（或 **Add file** -> **Upload files**）。
3. 將本資料夾內的所有檔案與資料夾（包含 `index.html`、`AGENTS.md`、`README.md`、`projects/`）直接拖曳進瀏覽器上傳。
4. 點擊下方綠色 **Commit changes** 按鈕。
5. 前往該 Repository 的 **Settings** -> 側邊欄點選 **Pages**。
6. 在 **Build and deployment** 下方的 **Branch** 選擇 `main` 分支並保持 `/ (root)`，點擊 **Save**。
7. 約等待 30 秒至 1 分鐘，重新整理頁面即可取得專屬公開網址！

### 方式 B：使用 Git 指令推播
```bash
cd my-portfolio
git init
git add .
git commit -m "feat: initial commit with AGENTS.md and portfolio"
git branch -M main
git remote add origin https://github.com/[YOUR-USERNAME]/my-portfolio.git
git push -u origin main
```
上傳後同樣前往 **Settings -> Pages** 啟用即可。

---

## 📄 授權與宣告 (License)
© 2026 Anita Li (李舲熏). All rights reserved.
專案代碼與架構依 MIT 授權條款開放參考。
