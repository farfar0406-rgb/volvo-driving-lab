# Volvo Driving Lab｜GitHub Pages 部署指引

**套件版本**：V9.15 公開版，繁體中文／English／한국어。三個語系共用相同的遊戲程式與 ES90、EX60、麋鹿模型，保留三種駕駛模式。

## 一、先檢查解壓縮後的結構

解壓縮 ZIP 後，應看到 `index.html`、`en.html`、`ko.html`、`game.js` 和 `models` 資料夾。`models` 裡需要有 `ES90_original.glb.gz`、`EX60_uniform_rear_rims.glb.gz`、`Low_Poly_Moose_Source.glb`。

**不要只上傳 ZIP，也不要只上傳 HTML。** GitHub Pages 必須拿到上述檔案與正確相對路徑。檔名大小寫需完全一致。

```
volvo-driving-lab/
├── index.html             # 繁體中文首頁
├── en.html                # 英文
├── ko.html                # 韓文
├── game.js                # 共用遊戲程式
├── models/
│   ├── ES90_original.glb.gz
│   ├── EX60_uniform_rear_rims.glb.gz
│   └── Low_Poly_Moose_Source.glb
├── .nojekyll
├── MOOSE_MODEL_CREDIT.txt
└── README.md
```

## 二、部署到既有 GitHub 儲存庫

若仍沿用先前的帳號與專案，可進入：

- 儲存庫：`https://github.com/farfar0406-rgb/volvo-driving-lab`
- 預期網站：`https://farfar0406-rgb.github.io/volvo-driving-lab/`

以上是依先前使用的帳號／儲存庫推定的網址，請以 GitHub Pages 設定畫面實際顯示為準。

### 方法 A：GitHub 網頁上傳（不安裝軟體）

1. 登入 GitHub，開啟 `volvo-driving-lab` 儲存庫的 **Code** 分頁。
2. 在根目錄按 **Add file → Upload files**，上傳 `index.html`、`en.html`、`ko.html`、`game.js`、`README.md`、`MOOSE_MODEL_CREDIT.txt`。如 `.nojekyll` 無法選取，可用 **Add file → Create new file** 建立 `.nojekyll`。
3. 保留 `models/` 資料夾：若 GitHub 上已有此資料夾，點進去，再用 **Add file → Upload files** 上傳三份模型。若沒有，先透過 **Create new file** 新建 `models/.gitkeep`，提交後點進 `models` 上傳三個模型，再視需要刪除 `.gitkeep`。
4. 頁面底部填入 Commit message，例如 `Publish multilingual Volvo Driving Lab`，按 **Commit changes**。
5. 回到 **Code**，確認根目錄能看到三份 HTML 和 `game.js`，而 `models` 資料夾內三個模型名稱正確。

> GitHub 官方說明：網頁上傳每個檔案上限為 **25 MiB**。本套件最大的模型檔案仍在此限制內。請勿把 ZIP 當成網站內容直接上傳。

### 方法 B：GitHub Desktop（較適合更新整包檔案）

1. 使用 GitHub Desktop 登入 GitHub，將 `volvo-driving-lab` 儲存庫 **Clone** 到電腦。
2. 解壓縮下載套件，把檔案與 `models/` 複製到該儲存庫的根目錄，允許覆蓋舊版 `index.html` 和模型檔。
3. 開啟 GitHub Desktop，在 **Changes** 確認修改內容，填入 Summary `Update multilingual public version`。
4. 按 **Commit to main**，接著按 **Push origin**，等待 GitHub 顯示上傳完成。

## 三、啟用 GitHub Pages

1. 在儲存庫上方選 **Settings**。
2. 左側選單找到 **Pages**。
3. 在 **Build and deployment**：**Source** 選 `Deploy from a branch`。
4. **Branch** 選 `main`，**Folder** 選 `/(root)`，再按 **Save**。若已是此設定，不用重複更改。
5. 稍後回到 Settings → Pages，按 **Visit site** 開啟網站。

GitHub 官方指出，更新有時需要最多約 **10 分鐘**才會出現在公開頁面。也可以到儲存庫的 **Actions** 檢查部署結果。

## 四、三個語言的網址

以先前的專案名稱為例：

- 繁體中文：`https://farfar0406-rgb.github.io/volvo-driving-lab/`
- English：`https://farfar0406-rgb.github.io/volvo-driving-lab/en.html`
- 한국어：`https://farfar0406-rgb.github.io/volvo-driving-lab/ko.html`

網站右上角也可點「繁中 / EN / 한국어」切換。三種語言的遊戲模式、加速數據與 AI 行為使用同一份程式。

## 五、上線前驗收

1. 分別開啟中文、英文、韓文網址，確認頁首語言切換與三個模式標題正常。
2. 進入「01 加速體驗」，選 EX60、ES90，確認模型可以顯示且 0–100 按鈕正常。
3. 進入「02 無限閃避」，確認車流、BLIS／AEB／LKA、音效與基本操作正常。
4. 進入「03 3D 賞車」，確認 EX60／ES90 原始材質及輪框正常，旋轉、縮放可用。
5. 用 Android 或 iPhone 再確認手機排版、音效，以及三個語言版本都可操作。

若顯示「車型載入失敗」：先確認 `models/` 的三個檔案已上傳且路徑正確，再嘗試 Chrome／Edge 強制重新整理（Windows：`Ctrl+Shift+R`）。如 GitHub Pages 尚未完成部署，請到 Actions 確認。

## 六、公開聲明與授權

此為非 Volvo 原廠官方作品，內容包含虛擬道路、加速與輔助系統示意，不構成真實安全性能承諾。麋鹿模型授權與作者註記已保留於網站及 `MOOSE_MODEL_CREDIT.txt`；其他車輛模型在公開前仍應確認其使用授權。

### 官方指引

- GitHub Pages 設定來源：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
- GitHub Pages 建站與檢視網址：https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site
- 使用網頁上傳檔案（25 MiB 上限）：https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository
