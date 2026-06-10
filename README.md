# Resume Studio · 高端简历工作台

> 一款面向职场人的本地端简历制作工具，无需注册，打开即用，数据完全存储在本地。

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-macOS%20%7C%20Windows%20%7C%20Browser-lightgrey.svg)
![Version](https://img.shields.io/badge/version-3.0-gold.svg)

---

## 特性

- **AI 智能导入** — 粘贴简历全文，由 DeepSeek AI 自动解析并填入所有字段，支持中英文混排
- **实时预览** — 左侧编辑，右侧即时渲染标准 A4 简历，所见即所得
- **10 套专业模板** — 经典、现代、极简、典雅、深色、紧凑、学院、蓝调、石板、正式
- **精细样式控制** — 字号、字体、配色、行高、间距全面可调
- **灵活布局** — 单栏 / 双栏自由切换，栏目拖拽排序，显示 / 隐藏独立控制
- **一键导出 PDF** — 输出标准 A4 格式，可直接投递
- **数据完全本地** — 所有内容存储在浏览器 localStorage，不上传任何服务器
- **JSON 导入导出** — 跨设备迁移简历数据

---

## 快速开始

### 方式一：直接使用（推荐）

1. 下载 html 文件
2. 用 Chrome 或 Edge 打开
3. 开始编辑

无需安装任何依赖，单文件即可运行。

### 方式二：在线使用

访问 https://resume-studio.gzl406633204.workers.dev/

---

## AI 智能导入

本工具使用 [DeepSeek API](https://platform.deepseek.com) 解析简历。

1. 点击顶部「✦ AI 导入」Tab
2. 填入你的 DeepSeek API Key（在 [platform.deepseek.com](https://platform.deepseek.com/api_keys) 免费获取）
3. 粘贴简历全文，点击「AI 智能解析并自动填入」

> API Key 仅存储在本地浏览器，不会上传。

---

## 内容模块

| 模块 | 说明 |
|------|------|
| 基本信息 | 姓名、职位、联系方式、照片、个人简介 |
| 工作经历 | 职位、公司、时间、城市、职责描述（支持多条） |
| 教育背景 | 学校、学历、专业、毕业年份、GPA |
| 专业技能 | 自定义分类，逗号分隔标签 |
| 项目经验 | 项目名称、角色、描述 |
| 荣誉证书 | 名称、颁发机构、时间 |
| 语言能力 | 语言、水平描述、熟练度进度条 |

---

## 模板一览

| 模板 | 风格 | 适用场景 |
|------|------|----------|
| 经典 | Playfair Display 衬线，暖白底 | 通用，外资企业 |
| 现代 | DM Sans 无衬线，纯白底 | 互联网，科技公司 |
| 极简 | Georgia 衬线，大留白 | 设计师，创意行业 |
| 典雅 | Lora 衬线，米色底 | 咨询，金融 |
| 深色 | 深蓝底，金色强调 | 高级管理，特殊场合 |
| 紧凑 | 无衬线，高密度 | 内容多，需压缩一页 |
| 学院 | EB Garamond，米黄底，大字号 | 学术，研究机构 |
| 蓝调 | 海军蓝主色，冷白底 | 政务，传统行业 |
| 石板 | Crimson Text，浅灰底 | 法律，医疗 |
| 正式 | 思源宋体，纯白 | 国企，政府机关 |

---

## macOS 桌面应用打包

如需打包为原生 macOS App（`.dmg`），参考以下步骤：

**前提：已安装 Node.js v20+**

```bash
# 克隆项目
git clone https://github.com/你的用户名/resume-studio.git
cd resume-studio/electron

# 配置国内镜像（中国用户）
cat > .npmrc << 'NPMRC'
registry=https://registry.npmmirror.com
electron_mirror=https://npmmirror.com/mirrors/electron/
electron_builder_binaries_mirror=https://npmmirror.com/mirrors/electron-builder-binaries/
NPMRC

# 安装依赖并打包
npm install --save-dev electron@28 electron-builder
./node_modules/.bin/electron-builder --mac --config.mac.identity=null
```

打包完成后在 `dist/` 目录找到 `.dmg` 文件。

> **提示**：如果打开时提示"已损坏"，在终端运行：
> ```bash
> xattr -cr /Applications/Resume\ Studio.app
> ```

---

## 键盘快捷键

| 快捷键 | 功能 |
|--------|------|
| `Cmd/Ctrl + P` | 导出 PDF |
| `Cmd/Ctrl + S` | 确认保存 |
| `Cmd/Ctrl + +` | 预览放大 |
| `Cmd/Ctrl + -` | 预览缩小 |

---

## HRBP 排版建议

- 3—5 年经验控制在 **1 页**，10 年以上最多 **2 页**
- 每条工作经历至少包含 **1 个量化数字**（如「营收增长 35%」）
- 工作经历按 **时间倒序** 排列，最新经历置顶
- 外资企业投递通常 **不放照片**，国内企业可保留
- 技能栏按类别归纳，避免堆砌关键词

---

## 技术栈

- 纯原生 HTML + CSS + JavaScript，无任何框架依赖
- AI 功能：[DeepSeek API](https://platform.deepseek.com)（deepseek-chat 模型）
- 桌面端：[Electron](https://www.electronjs.org/) v28
- 字体：Google Fonts（Playfair Display、DM Sans、Lora、EB Garamond、Crimson Text、Noto Serif/Sans SC）

---

## License

[MIT](./LICENSE) © 2025 Resume Studio

---

<p align="center">如果这个项目对你有帮助，欢迎 Star ⭐</p>
