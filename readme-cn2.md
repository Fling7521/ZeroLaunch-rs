

<div align="center">
<!--
    <p align="center">
         <img src="./Web/src/assets/logo.png" height="128" alt="ZeroLaunch-logo"/> 
    </p>
-->
    <h1>🚀 ZeroLaunch-rs 🚀</h1>
</div>

<div align="center"><h3>✨ 極速精準、輕量純粹的 Windows 應用程式啟動器！✨</h3></div>

<div align="center">

![Platform](https://img.shields.io/badge/Platform-Windows_11-0078d7?logo=windows11&logoColor=white)
[![GPLv3 License](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![Gitee star](https://gitee.com/ghost-him/ZeroLaunch-rs/badge/star.svg?theme=dark)](https://gitee.com/ghost-him/ZeroLaunch-rs/stargazers)
[![GitHub stars](https://img.shields.io/github/stars/ghost-him/ZeroLaunch-rs.svg?style=social)](https://github.com/ghost-him/ZeroLaunch-rs/stargazers)
[![GitCode stars](https://gitcode.com/ghost-him/ZeroLaunch-rs/star/badge.svg)](https://gitcode.com/ghost-him/ZeroLaunch-rs/stargazers)

</div>

<div align="center">

[简体中文](README.md) | [繁體中文](readme-cn2.md) | [English](readme-en.md)

</div>


<div align="center">
    <a href="https://gitee.com/ghost-him/ZeroLaunch-rs" target="_blank">Gitee</a> •
    <a href="https://github.com/ghost-him/ZeroLaunch-rs" target="_blank">GitHub</a> •
    <a href="https://gitcode.com/ghost-him/ZeroLaunch-rs" target="_blank">GitCode</a>
</div>

## 📕 一句話介紹

ZeroLaunch 是一款專為 Windows 平台精心打造的應用程式啟動器，致力於提供極致高效、快捷的搜索體驗，讓您瞬間找到並啟動所需應用。

> 該項目因個人需要而開發，因此該項目將持續維護與優化，確保其長期穩定運行與功能完善。

## 🖥️ 軟件界面

[![主界面預覽](asset/主界面.png)](asset/picture-cn.md)  
*點擊圖片查看完整功能截圖集*

**背景圖片可自定義**

## ✨ 核心特性

### 🔒 隱私至上
完全離線運行，無需網絡連接，您的數據始終保留在設備中。我們堅持零數據採集原則，嚴格遵循本地化處理，確保您的信息安全。

### ⚡ 智能搜索
採用三重匹配技術（全稱/模糊/拼音），支援中英文混合查詢，配合實時動態排序算法和多線程併發處理，帶來流暢高效的搜索體驗。

### 🌐 輕巧純粹
專注於應用程式搜索功能，簡潔而不簡單，為您提供精準、快速的結果。

## 🚩 程式下載

* Gitee: [release](https://gitee.com/ghost-him/ZeroLaunch-rs/releases)
* Github: [release](https://github.com/ghost-him/ZeroLaunch-rs/releases)
* Gitcode: [release](https://gitcode.com/ghost-him/ZeroLaunch-rs/releases)

## 🚀 快速入門

### 快捷鍵速查

| 功能                | 快捷鍵           |
|---------------------|------------------|
| 呼出搜索欄          | `Alt + Space`    |
| 上下選擇項目        | `↑/↓` 或 `Ctrl+k/j` |
| 啟動選中程式        | `Enter`          |
| 管理員權限啟動      | `Ctrl + Enter`   |
| 清空搜索框          | `Esc`            |
| 隱藏搜索界面        | 點擊外部區域      |

### 三步配置同步

1. **選擇同步目錄**
   進入設置 → 其他設置 → 選擇目標路徑（推薦使用網盤同步目錄）

2. **自動同步配置**

```plaintext
    [同步目錄]
        ├── ZeroLaunch_remote_config.json      # 程式配置
        └── background.jpg   # 背景圖片
```

3. **多設備共享**

在其他設備安裝後指向同一目錄即可同步所有設置

## ⚙️ 高級配置

### 路徑管理策略

搜索路徑示例：

```plaintext
C:\Program Files\ (深度5層)
├── App1/              ✔️ 索引
│   └── Subfolder/     ✔️ 索引
└── App2/
 └── .../
     └── Layer5/    ✔️ 索引 (第5層)
         └── Layer6 ❌ 忽略
```

#### 排除規則：

使用前綴完全匹配機制，例如排除 `C:\Temp` 將阻止所有以該路徑開頭的目錄索引

#### 權重調優公式

程式的最終權重 = 算法匹配度 + ∑(關鍵字權重)

示例配置：

|關鍵字	|權重|	效果|
|---|---|---|
|解除安裝|-5000|完全排除解除安裝程式|
|beta|+2.5|提升測試版優先級|
|文件|-1.0|降低文件類結果排序|

## 🛠️ 開發者指南

### 環境要求

* Rust v1.82.0
* Node.js v22.11.0
* Bun v1.2.3

### 構建步驟

```bash
# 克隆倉庫
git clone https://github.com/ghost-him/ZeroLaunch-rs.git

# 安裝依賴
bun install

# 開發模式
bun run tauri dev

# 生產構建
bun run tauri build
```

構建產物路徑：`./src-tauri/target/release/`

## 📦 數據目錄結構

```
%APPDATA%\ZeroLaunch-rs\
├── logs/                               # 運行日誌
└── ZeroLaunch_local_config.json        # 配置文件的存放地址
```

## 📌 已知限制

### 短詞搜索

⚠️ 輸入長度 < 3 字元時，搜索結果可能不夠精確

## 🤝 開源致謝

本專案基於以下優秀開源專案構建：

* [chinese-xinhua](https://github.com/pwxcoo/chinese-xinhua) - 中文轉拼音核心詞典
* [LaunchyQt](https://github.com/samsonwang/LaunchyQt) - UWP應用索引方案
* [icon-icons](https://icon-icons.com/zh/) - 提供了該程式的圖標

## 🎯 待辦事項

### 軟體目標

* 使用正則表達式來做關鍵字屏蔽與路徑屏蔽
* 支援自定義搜尋資料夾深度
* 添加一鍵恢復預設的設定檔保存地址
* 自定義一鍵執行的命令（key+命令的形式，內建可能會用到的命令，預設不開啟）
* 暗色主題
* 調試功能（比如，可以查看搜尋演算法執行的結果，臨時添加搜尋的條目，可以查看關鍵字生成演算法的執行結果，效能評估）
* 當用戶打開了搜尋欄時，不要更新資料庫
* uwp 應用還存在部分無法索引的問題，尚未確定原因
* 錯誤處理優化

### 長期目標

> 當以上目標都完成時才開始實現以下功能

* 支援linux系統（wayland優先）

**以上內容由 DeepSeek-R1 完成轉換**