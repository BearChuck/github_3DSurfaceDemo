# 🎴 3D Holographic Foil TCG Card Showcase | 個人專屬 3D 鐳射反光卡牌展示網頁

![GitHub Pages Status](https://img.shields.io/badge/GitHub%20Pages-Live%20Demo-brightgreen?style=for-the-badge&logo=github)
![Single File Architecture](https://img.shields.io/badge/Architecture-Single--file%20All--in--One-blueviolet?style=for-the-badge)
![Zero Dependencies](https://img.shields.io/badge/Dependencies-Zero%20Build%20Required-orange?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

一個高質感、具備 **3D 視差矩陣（CSS 3D Parallax Matrix）** 與 **動態鐳射反光（Holographic Foil Shader Layer）** 的傳奇集換式卡牌（TCG）展示與客製化產生器。

專為 **GitHub Pages** 靜態 Demo 設計，符合「單一檔案 `index.html`、零建置依賴、開箱即用」，支援完整響應式網頁設計（RWD）、行動端觸控與陀螺儀感應，並提供一鍵 PNG 高解析度圖片匯出。

🌐 **Live Demo 即時展示**: [https://bearchuck.github.io/github_3DSurfaceDemo/](https://bearchuck.github.io/github_3DSurfaceDemo/)

---

## ✨ 核心特色 (Key Features)

### 1. 📱 響應式佈局與跨裝置適配 (RWD Architecture)
- **桌面與寬螢幕 (≥ 1024px)**：雙欄並排（Side-by-Side）設計。左側為 3D 卡牌即時互動舞台（具備滾動黏性居中與視差空間），右側為磨砂玻璃風格 (Glassmorphism) 的控制與自訂面板。
- **平板與筆電 (768px - 1023px)**：流體縮放邊距與等比卡牌計算。
- **行動裝置與直立手機 (< 768px)**：自動切換為垂直單欄堆疊與單手觸控友善面板。卡牌部位於上半部視覺黃金區。
- **經典 TCG 黃金比例**：嚴格引用 TCG 標準比例（`63mm × 88mm`，約 `1 : 1.4`），搭配 `cqw` 容器查詢單位（Container Query Units）與 `clamp()`，確保卡面內文在各尺寸下皆保持精準對齊與清晰可讀性。

---

### 2. 🎴 傳奇集換式卡牌 5 大核心結構
1. **頂部 Header**：卡牌名稱、生命數值（HP）、核心屬性徽章（🔮 精神 / ⚙️ 科技 / ⚡ 疾速 / 🔥 創發 / 🍃 生態 / 💎 傳奇）與位階標記（`STAGE 2 MASTER`）。
2. **核心插畫視窗 Artwork Window**：支援「經典幾何金屬框格」與「滿版全圖 (SAR / Full Art)」模式切換；預設科技風格 SVG 向量立繪，並支援本機照片上傳預覽（FileReader API 純前端處理）。
3. **特質與招式 Body**：
   - **特性（Passive）**：【深度專注・Hyperfocus】
   - **核心招式（Skill 1）**：消耗能量圖示、【架構重構・System Refactor】、傷害數值 `120+` 及文字敘述。
   - **奧義技能（Ultimate）**：【超限思維・Limitless Innovation】、高額傷害 `260` 及效果描述。
4. **對抗數值 Footer**：弱點（🔥 ×2）、抗性（🛡️ -30）、撤退/調度成本（⚪ ⚪）。
5. **防偽與認證 Meta**：創作者署名、卡牌稀有度編號（`No. 001/001 ★★★ SAR`）、年份與「1st Edition」首刷金屬印記。

---

### 3. 🌈 3D 視差與動態鐳射全息箔膜 (Holographic Foil Shader)
- **CSS 3D Transform 矩陣**：使用 `preserve-3d` 與 `perspective: 1200px`，隨游標或觸控偏移即時計算 `rotateX` 與 `rotateY`（-16deg 至 +16deg），移開時平滑回彈。
- **4 種動態全息箔膜 Shader**：
  - 🌌 **Cosmos Holo**（宇宙星雲彩虹）：漸變光斑與星點閃爍折射。
  - 🌈 **Rainbow Secret**（彩虹極光光束）：霓虹彩斑與極光折射。
  - 👑 **Gold Ultra**（黑金高奢浮雕）：高奢黑金屬金屬浮雕質感。
  - ❄️ **Silver Phantom**（冷冽銀鏡暗光）：冷冽銀色冷光賽博朋克質感。
- **行動端陀螺儀感應 (DeviceOrientation)**：微幅傾斜手機即可產生實體重力感反光與 3D 傾角（支援 iOS Safari 權限請求機制）。

---

### 4. 🛠️ 即時編輯與高解析度匯出
- **雙向即時編輯**：支援點擊卡牌文字直接打字編輯（`contenteditable="true"`），或經由右側控制面板同步修改。
- **本機圖片上傳**：拖曳或點擊上傳個人肖像，純前端處理，不需任何伺服器。
- **一鍵匯出 PNG**：調用 `html2canvas` 直接將專屬卡牌渲染為高解析度無失真 PNG 圖片。
- **3D 180 度翻轉**：一鍵翻轉至黑金幾何科技卡背。
- **傳奇職涯範本**：預設「首席系統架構師」、「AI 模型工程大師」、「全端開發傳奇」、「創發 UI/UX 總監」一鍵切換。

---

## 🚀 部署指南 (Deploy to GitHub Pages)

本專案採用 **Single-file All-in-One** 架構，只需上傳至 GitHub 並開啟 GitHub Pages 即可運行：

```bash
# 1. 克隆或進入專案目錄
git clone https://github.com/BearChuck/github_3DSurfaceDemo.git
cd github_3DSurfaceDemo

# 2. 提交修改
git add .
git commit -m "Update README"
git push origin main
```

開啟 GitHub Pages 服務：
1. 前往 GitHub 倉庫的 **Settings** -> **Pages**。
2. 將 **Source** 設定為 `Deploy from a branch`。
3. Branch 選擇 `main` / `/ (root)` 並點擊 **Save**。
4. 約 1 分鐘後即可經由 `https://<your-username>.github.io/<repo-name>/` 存取。

---

## 💻 技術棧 (Tech Stack)

- **Core**: HTML5, CSS3, Vanilla JavaScript (ES6+)
- **Styling & Layout**: Vanilla CSS (CSS Grid, Flexbox, Container Queries `cqw`, CSS Variables, Glassmorphism)
- **3D & Shaders**: CSS 3D Transforms (`preserve-3d`, `rotateX/Y`), Dynamic Gradient Shaders (`mix-blend-mode: color-dodge`)
- **Export Library**: `html2canvas` (via cdnjs CDN)
- **Typography**: Google Fonts (`Cinzel`, `Outfit`, `Space Grotesk`)
- **Icons**: Font Awesome 6.5.1

---

## 📄 授權條款 (License)

本專案採用 [MIT License](LICENSE) 授權。歡迎自由 Fork、修改與分享！

---

<p center="align">
  Crafted with ❤️ by <a href="https://github.com/BearChuck">BearChuck</a>
</p>
