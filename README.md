# 英文學習系統

<div align="center">

一個功能完整的英文學習平台，整合 YouTube 影片學習、個人化單字庫管理、間隔重複學習算法等功能。

[![Python](https://img.shields.io/badge/Python-3.13+-blue.svg)](https://www.python.org/)
[![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)](https://flask.palletsprojects.com/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

[功能特色](#-功能特色) • [快速開始](#-快速開始) • [使用說明](#-使用說明) • [技術架構](#-技術架構) • [貢獻](#-貢獻)

</div>

---

## 📖 簡介

英文學習系統是一個專為英語學習者設計的互動式學習平台。透過 YouTube 影片提供沉浸式學習體驗，支援雙語字幕同步顯示、單字查詢、個人單字庫管理、智慧複習等功能，幫助您更有效率地學習英語。

### 主要特色

- 🎥 **YouTube 影片整合**：支援所有 YouTube 影片，自動獲取並翻譯字幕
- 📝 **雙語字幕同步**：英中對照字幕，與影片播放時間精確同步
- 🔍 **智慧單字查詢**：點擊字幕即可查看單字詳細資訊、發音、例句
- 📚 **個人單字庫**：建立多個單字庫，管理個人學習內容
- 🎯 **間隔重複學習**：採用科學的間隔重複算法，提升記憶效率
- 🏆 **學習統計**：追蹤學習時間、進度，支援排行榜功能
- 🎨 **響應式設計**：支援各種設備，提供流暢的使用體驗

## ✨ 功能特色

### 核心學習功能

- **YouTube 影片播放**：支援所有 YouTube 影片格式
- **字幕同步顯示**：自動獲取影片字幕，同步顯示英文和中文翻譯
- **時間跳轉**：點擊字幕可跳轉到對應的播放時間點
- **單字高亮**：跟隨影片播放進度，自動高亮當前單字

### 單字管理

- **單字查詢**：點擊字幕中的單字即可查看詳細資訊（翻譯、音標、詞性、例句、同義詞）
- **發音播放**：支援單字和例句的語音播放
- **單字庫管理**：建立多個個人化單字庫，分類管理學習內容
- **匯出/匯入**：支援單字庫的匯出和匯入（JSON 格式）

### 學習功能

- **智慧複習**：間隔重複學習算法，根據記憶曲線安排複習
- **學習統計**：追蹤學習時間、複習次數、準確率等數據
- **排行榜**：學習時間榜和複習成績榜，與其他學習者一起進步
- **書籤系統**：收藏常用影片，快速存取

### 用戶體驗

- **布局切換**：支援左右布局（寬螢幕）和上下布局（窄螢幕）
- **字幕控制**：調整字幕行數、顯示/隱藏中英文、時間偏移調整
- **影片控制**：調整影片大小、自動滾動字幕
- **響應式設計**：適配各種螢幕尺寸

## 🚀 快速開始

### 系統需求

- Python 3.13 或更高版本
- 穩定的網路連線（用於影片播放和翻譯）
- 現代化瀏覽器（Chrome、Firefox、Safari、Edge）

### 安裝步驟

1. **克隆專案**

```bash
git clone https://github.com/yourusername/english_learning.git
cd english_learning
```

2. **安裝依賴**

```bash
pip install -r requirements.txt
```

3. **啟動應用**

```bash
# 推薦方式（自動檢查依賴）
python run.py

# 或直接運行
python app.py
```

4. **開啟瀏覽器**

訪問 `http://localhost:5000`

## 📖 使用說明

### 基本使用流程

1. **載入影片**
   - 在輸入框中貼上 YouTube 影片網址
   - 點擊「載入影片」按鈕
   - 等待字幕載入完成

2. **開始學習**
   - 播放影片，字幕會自動同步顯示
   - 點擊字幕中的單字查看詳細資訊
   - 將重要單字加入個人單字庫

3. **複習單字**
   - 進入「單字庫」→「複習單字」
   - 選擇複習模式（間隔重複或隨機複習）
   - 系統會根據學習記錄安排複習內容

### 快捷操作

- **Enter 鍵**：在輸入框中按 Enter 鍵快速載入影片
- **點擊字幕**：點擊字幕跳轉到對應的播放時間
- **ESC 鍵**：關閉單字資訊視窗

### 詳細功能說明

詳細的使用說明請參考 [使用手冊](USER_GUIDE.md)。

## 🛠️ 技術架構

### 技術棧

- **前端**
  - HTML5, CSS3, JavaScript (ES6+)
  - YouTube IFrame API
  - 響應式設計

- **後端**
  - Flask (Python Web 框架)
  - yt-dlp (字幕獲取)
  - Google Translate API (翻譯服務)
  - Google Text-to-Speech API (語音合成)

- **數據存儲**
  - JSON 文件存儲（單字庫、用戶數據、快取）

### 專案結構

```
english_learning/
├── app.py                 # Flask 主應用程式
├── run.py                 # 啟動腳本（自動檢查依賴）
├── requirements.txt       # Python 依賴
├── templates/
│   └── index.html        # 主頁面模板
├── static/
│   ├── style.css         # 樣式文件
│   └── script.js         # 前端邏輯
├── word_banks.json       # 單字庫數據
├── user_data.json        # 用戶學習統計
├── subtitle_cache.json   # 字幕快取
├── translation_cache.json # 翻譯快取
└── bookmarks.json        # 書籤數據
```

## 📝 開發

### 環境設置

```bash
# 安裝開發依賴
pip install -r requirements.txt

# 啟動開發伺服器
python run.py
```

### 打包為可執行檔

```bash
# Windows
build_exe.bat

# 或使用 PyInstaller
pyinstaller english_learning.spec
```

## 🤝 貢獻

歡迎貢獻！請遵循以下步驟：

1. Fork 本專案
2. 建立功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 開啟 Pull Request

## 📄 授權

本專案採用 MIT 授權條款。詳見 [LICENSE](LICENSE) 文件。

## 👤 作者

**Craig Huang**

- Email: craig7351@gmail.com
- GitHub: [@yourusername](https://github.com/yourusername)

## 🙏 致謝

- [yt-dlp](https://github.com/yt-dlp/yt-dlp) - YouTube 影片和字幕下載
- [Flask](https://flask.palletsprojects.com/) - Python Web 框架
- [deep-translator](https://github.com/nidhaloff/deep-translator) - 翻譯服務

## 📚 相關文件

- [使用手冊](USER_GUIDE.md) - 詳細的使用說明
- [更新記錄](CHANGELOG.md) - 版本更新歷史

## ⚠️ 注意事項

- 📡 需要網路連線才能使用（影片播放、字幕獲取、翻譯）
- 🎥 部分影片可能沒有字幕或字幕不可用
- 🌐 翻譯品質取決於 Google Translate 的準確度
- ⏳ 首次載入字幕可能需要等待（特別是長影片）
- 💾 學習資料儲存在本地 JSON 文件中，建議定期備份

## 🔮 未來計劃

- [ ] 改進單字高亮算法，提高準確度
- [ ] 改進間隔重複學習算法
- [ ] 支援多語言字幕
- [ ] 添加字幕下載功能

詳見 [更新記錄](CHANGELOG.md) 了解最新功能和改進。

---

<div align="center">

**如果這個專案對您有幫助，請給一個 ⭐ Star！**

Made with ❤️ by Craig Huang

</div>
