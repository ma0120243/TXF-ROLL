# 📊 TXFM ROLL — 期貨滾倉策略計算工具

微型台指期(及其他台指期商品)的滾倉策略計算工具。以「風險指標(RI)」為核心,自動計算加碼、減碼、鎖利的精確觸發點位。

純前端 HTML/JS,**無需後端、無需安裝**,可離線使用、可加入手機主畫面當 App。

---

## ✨ 功能

- **6 大分頁**:參數設定 / 加碼表 / 減碼表 / 鎖利表 / 走勢圖 / 策略庫
- **風險指標(RI)** 區間寬容機制(加碼上限、減碼下限可自訂)
- **真實損益計算**:加碼後均價上移、減碼後實現損益,完全精準
- **雙向觸發點**:加碼表同時顯示「若回跌何時減碼、要減幾口、可容忍多少」
- **三種下跌策略**:直接減碼 / 補保證金 / 混合
- **鎖利機制**:每 N 次加碼自動鎖定獲利
- **7 種商品**:微台、小台、大台、中型100、小電子、小金融、自訂
- **策略庫**:儲存多套設定(保守型/激進型/長線型),可匯出匯入
- **PWA**:可加入手機主畫面、離線使用

---

## 🚀 部署到 GitHub Pages(3 步驟)

### 步驟 1:建立 Repository
1. 登入 GitHub,點右上角 **＋ → New repository**
2. Repository name 填寫(例如 `txfm-roll`)
3. 設為 **Public**(GitHub Pages 免費版需公開)
4. 點 **Create repository**

### 步驟 2:上傳檔案
1. 在新建的 repo 頁面,點 **uploading an existing file**
2. 把這個資料夾裡的**所有檔案**拖進去:
   - `index.html`
   - `manifest.json`
   - `sw.js`
   - `icon-192.png`
   - `icon-512.png`
   - `.nojekyll`
3. 點 **Commit changes**

### 步驟 3:開啟 GitHub Pages
1. 進入 repo 的 **Settings** → 左側 **Pages**
2. Source 選 **Deploy from a branch**
3. Branch 選 **main**(或 master)、資料夾選 **/ (root)**
4. 點 **Save**
5. 等 1~2 分鐘,頁面會顯示你的網址:
   ```
   https://你的帳號.github.io/txfm-roll/
   ```

完成!打開那個網址就能使用,手機也可以。

---

## 📱 加入手機主畫面(當 App 用)

### iPhone(Safari)
1. 用 Safari 開啟你的 GitHub Pages 網址
2. 點下方「分享」按鈕
3. 選「加入主畫面」

### Android(Chrome)
1. 用 Chrome 開啟網址
2. 點右上選單(三個點)
3. 選「安裝應用程式」或「加到主畫面」

---

## 💻 本機使用(不部署)

直接雙擊 `index.html` 即可用瀏覽器開啟。
(注意:本機開啟時 PWA 離線功能與「加入主畫面」可能受限,建議部署到 GitHub Pages 或用支援的本機伺服器)

---

## 🔄 更新版本

修改 `index.html` 後重新上傳,並把 `sw.js` 裡的 `CACHE_NAME` 改一個新版本號(例如 `txfm-roll-v3-3`),否則瀏覽器可能用舊快取。

使用者端若沒看到更新,可在 App 內點「🔥 強制重整」或瀏覽器按 `Ctrl+Shift+R`。

---

## ⚠️ 免責聲明

本工具僅為交易策略的**計算輔助**,不含手續費、交易稅、滑價與隔夜跳空風險。所有計算結果僅供參考,不構成投資建議。期貨交易具高度槓桿風險,可能導致超過本金的損失。實際交易決策請依自身風險承受能力與券商規定為準,作者不負任何投資損益責任。

---

## 📂 檔案結構

```
txfm-roll/
├── index.html       # 主程式(所有功能都在這)
├── manifest.json    # PWA 設定
├── sw.js            # Service Worker(離線快取)
├── icon-192.png     # App 圖示
├── icon-512.png     # App 圖示(高解析)
├── .nojekyll        # 告訴 GitHub 不要用 Jekyll 處理
└── README.md        # 本說明檔
```

技術:純 HTML + CSS + 原生 JavaScript,無外部相依套件。資料儲存於瀏覽器 localStorage。
