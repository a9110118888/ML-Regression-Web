# 50 Startups 多元線性回歸探索器 (Multiple Linear Regression Explorer)

一個專為 **GitHub Pages** 設計的純前端 (Pure Frontend: HTML5 / Vanilla CSS / Modern JavaScript) 統計機器學習探索應用。

---

## 🌟 核心特色與功能架構

1. **專業現代儀表板 (Modern Dashboard UI)**
   - 深色導覽列（Dark Header Bar）、漸層質感品牌標誌、即時狀態徽章。
   - 4 大關鍵指標卡片 (KPI Cards)：觀測樣本數 (50)、決定係數 ($R^2$ 95.08%)、均方根誤差 (RMSE $8,855)、最強顯著特徵 (R&D Spend, $t=17.37$)。
   - 卡片式佈局 (Cards Layout)、精緻陰影與微互動懸浮效果。

2. **資料集輸入區 (Dataset Source & Fallback Engine)**
   - 預設填入開源資料集 GitHub Raw URL：
     `https://raw.githubusercontent.com/krishnaik06/Multiple-Linear-Regression/master/50_Startups.csv`
   - 提供「**載入資料**」按鈕，透過 `fetch()` 動態獲取。
   - 內建完整 50 筆 Startup 企業備用資料庫，若遭遇瀏覽器跨來源 (CORS) 限制或離線環境，將**自動無縫切換**為內建資料庫，保證 100% 穩定運作。

3. **問題切換下拉選單 (Problem Switcher Dropdown)**
   - 提供 `<select id="problemSelector">` 包含：
     - **Problem 1: 特徵選擇與模型分析** (Feature Selection & Model Diagnostics)
     - **Problem 2: 即時利潤預測** (Real-time Profit Prediction)
   - 切換時下方區塊平滑淡入切換，並自動重新調適圖表尺寸。

4. **純前端 OLS 最小平方法矩陣運算引擎 (Pure JS Linear Algebra Engine)**
   - 包含矩陣轉置 ($X^T$)、矩陣乘法 ($A \times B$)。
   - 實作 **高斯-若爾當消去法 (Gauss-Jordan Elimination)** 搭配主元選擇 (Partial Pivoting) 計算 $(X^TX)^{-1}$。
   - 計算回歸係數向量：
     $$\hat{\beta} = (X^T X)^{-1} X^T y$$
   - 實作 **Lanczos 近似 $\Gamma(z)$ 與連分數法正規化不完全 Beta 函數 $I_x(a, b)$**，精準計算 Student's $t$ 分配雙尾 $p$-value 與整體回歸模型 $F$ 統計量 $p$-value。

5. **圖表與統計表格展示 (Charts & Diagnostics Tables)**
   - **特徵數量與 RMSE 關係圖 (Chart.js)**：比較從 1 個特徵至 5 個特徵 (全模型) 的 RMSE 與 Adjusted $R^2$ 走勢，視覺化呈現多餘變數對模型泛化能力的懲罰效應。
   - **實際利潤 vs 預測利潤擬合圖**：散佈點與 $y = x$ 理想對角參考線。
   - **回歸模型係數估計表**：特徵名稱、估計係數 ($\hat{\beta}$)、標準誤 ($SE$)、$t$ 統計量、$p$-value、顯著性標籤 (`***`, `**`, `*`, `.`, `n.s.`)。
   - **殘差五數診斷**：Min、1Q、Median、3Q、Max、殘差自由度、F 檢定。

6. **即時預測器 (Real-time Profit Predictor)**
   - 提供互動拉桿 (Sliders) 與連動數字輸入框：
     - 研發支出 (R&D Spend): $0 ～ $250,000
     - 管理費用 (Administration): $0 ～ $250,000
     - 行銷支出 (Marketing Spend): $0 ～ $500,000
     - 公司州別 (State): New York / California / Florida (虛擬變數 One-hot Encoding)
   - 即時預測利潤 Hero Card、95% 預測信賴區間、預估 ROI 計算。
   - **邊際貢獻分解圖 (Waterfall Chart)** 與 **實時代入方程式字串**。
   - 提供「科技獨角獸」、「行銷導向電商」、「穩健擴張新創」、「精實種子團隊」4 種一鍵情境範本。

---

## 🚀 如何部署至 GitHub Pages (1 分鐘快速部署)

1. **建立 GitHub 儲存庫 (Repository)**：
   - 在 GitHub 上建立一個新的公開儲存庫 (例如 `50-startups-regression-explorer`)。
2. **上傳本專案檔案**：
   - 將 [index.html](file:///c:/Users/DODO/Desktop/Multiple_Regression_Web/index.html) 推送至該儲存庫的 `main` 分支根目錄。
3. **啟用 GitHub Pages**：
   - 進入儲存庫的 **Settings** -> **Pages**。
   - 在 **Build and deployment** > **Branch** 選擇 `main` 分支與 `/ (root)` 資料夾，點選 **Save**。
4. **開啟網頁**：
   - 稍候約 30 秒，GitHub Pages 即會產生可供全球訪問的公開網址（例如 `https://<你的帳號>.github.io/50-startups-regression-explorer/`）。
