# ZeroLaunch-rs 🚀

[![GPLv3 License](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
![Platform](https://img.shields.io/badge/Platform-Windows-0078d7)
![Rust](https://img.shields.io/badge/Rust-1.72%2B-orange)
[![GitHub](https://img.shields.io/badge/GitHub-Repository-blue?logo=github)](https://github.com/ghost-him/ZeroLaunch-rs) 
[![Gitee](https://img.shields.io/badge/Gitee-仓库-red?logo=gitee)](https://gitee.com/ghost-him/zero-launch-rs)
![GitHub Stars](https://img.shields.io/github/stars/ghost-him/ZeroLaunch-rs?style=social)

现代化的Windows快速启动工具，使用 Rust + Tauri + Vue.js 构建

[![主界面预览](asset/主界面.png)](asset/picture.md)  
*点击图片查看完整功能截图集*

## ✨ 核心特性

### 🔒 隐私优先设计

- 完全离线运行 - 无需网络连接，数据永不外传
- 零数据采集 - 严格遵循本地化原则

### ⚡ 智能搜索体验

- 三重匹配引擎：全称/模糊/拼音
- 中英文混合搜索支持
- 实时动态排序算法
- 多线程并发搜索

### 🌐 跨设备同步

- 配置文件云同步
- 智能路径权重管理
- 背景主题自定义

## 🚀 快速入门

### 快捷键速查

| 功能                | 快捷键           |
|---------------------|------------------|
| 呼出搜索栏          | `Alt + Space`    |
| 上下选择项目        | `↑/↓` 或 `Ctrl+k/j` |
| 启动选中程序        | `Enter`          |
| 管理员权限启动      | `Ctrl + Enter`   |
| 清空搜索框          | `Esc`            |
| 隐藏搜索界面        | 点击外部区域      |

### 三步配置同步

1. **选择同步目录**
   进入设置 → 其他设置 → 选择目标路径（推荐使用网盘同步目录）

2. **自动同步配置**

```plaintext
    [同步目录]
        ├── config.json      # 程序配置
        └── background.jpg   # 背景图片
```

3. **多设备共享**

在其他设备安装后指向同一目录即可同步所有设置

## ⚙️ 高级配置

### 路径管理策略

搜索路径示例：

```plaintext
C:\Program Files\ (深度5层)
├── App1/              ✔️ 索引
│   └── Subfolder/     ✔️ 索引
└── App2/
 └── .../
     └── Layer5/    ✔️ 索引 (第5层)
         └── Layer6 ❌ 忽略
```

#### 排除规则：

使用前缀完全匹配机制，例如排除 `C:\Temp` 将阻止所有以该路径开头的目录索引

#### 权重调优公式

程序的最终权重 = 算法匹配度 + ∑(关键词权重)

示例配置：

|关键词	|权重|	效果|
|---|---|---|
|卸载|-5000|完全排除卸载程序|
|beta|+2.5|提升测试版优先级|
|文档|-1.0|降低文档类结果排序|

## 🛠️ 开发者指南

### 环境要求

* Rust
* Node.js
* Bun

### 构建步骤

```bash
# 克隆仓库
git clone https://github.com/ghost-him/ZeroLaunch-rs.git

# 安装依赖
bun install

# 开发模式
bun run tauri dev

# 生产构建
bun run tauri build
```

构建产物路径：`./src-tauri/target/release/`

## 📦 数据目录结构

```
%APPDATA%\ZeroLaunch-rs\
├── logs/                               # 运行日志
└── ZeroLaunch_local_config.json        # 配置文件的存放地址
```

## 📌 已知限制

### 短词搜索

⚠️ 输入长度 < 3 字符时，搜索结果可能不够精确

## 🤝 开源致谢

本项目基于以下优秀开源项目构建：

* [chinese-xinhua](https://github.com/pwxcoo/chinese-xinhua) - 中文转拼音核心词典
* [Bootstrap Icons](https://icons.getbootstrap.com/) - 界面图标资源
* [LaunchyQt](https://github.com/samsonwang/LaunchyQt) - UWP应用索引方案

## 🎯 todo

doing: 重构软件代码，提高软件的可维护性

* 重新设计运行界面
* 使用正则表达式来做关键字屏蔽与路径屏蔽
* 支持自定义搜索文件夹深度
* 主题颜色随背景图片的改动而改动
* 添加一键恢复默认的配置文件保存地址
* 重构软件代码，提高软件的可维护性
* 暗色主题