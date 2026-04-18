# Tab Out

**让标签页井井有条。**

[English](README.md) · [简体中文](README-CN.md)

Tab Out 是一个 Chrome 扩展，把新标签页替换成一个仪表盘，集中展示你当前打开的所有标签页。标签按域名（或 Chrome 标签组）分组，常用首页（Gmail、X、LinkedIn 等）会被归入单独的卡片。关闭标签时还有满足感十足的 swoosh 音效和彩带特效。

无服务端、无账号、无外部 API 调用，只是一个 Chrome 扩展。

> 本仓库是 [zarazhangrui/tab-out](https://github.com/zarazhangrui/tab-out) 的功能增强分支，新增了 bento 布局、暗色模式、搜索栏、Quick Access、Bing 每日背景、Chrome 标签组视图等能力。

---

## 用编程 Agent 一键安装

把这个仓库地址发给你的编程 Agent（Claude Code、Codex 等），说 **"install this"**：

```
https://github.com/arbing/tab-out
```

Agent 会带你走完全部步骤，大约 1 分钟。

---

## 功能特性

### 标签页管理
- **一屏看尽所有标签页**，清爽的 bento 网格布局
- **两种分组模式**：域名视图与 Chrome 标签组视图一键切换
- **首页卡片**：把 Gmail、X、YouTube、LinkedIn、GitHub 等首页集中到一个卡片
- **自定义分组**：为你关心的域名定义自己的分组规则
- **重复标签检测**：发现同一页面被打开多次，一键清理
- **点击标签直接跳转**：跨窗口跳转，不会新建标签页
- **Localhost 分组**：本地项目按端口号区分，再也不会搞混
- **可展开分组**：默认展示前 N 个标签，剩余通过 "+N more" 展开
- **受保护标签**：固定（pinned）标签与独立窗口标签会带徽标和独立的关闭按钮，避免被 "关闭全部" 误伤

### 效率提升
- **搜索栏**：按标题或 URL 过滤当前标签页，支持 `/` 快捷键聚焦
- **Quick Access 卡片**：把你常用的快捷入口固定在页面顶部
- **书签集成**：把 Chrome 书签和打开的标签页放在一起浏览
- **稍后再看**：在关闭前把标签收藏到清单，并支持归档视图

### 外观体验
- **Bento 布局**：自适应的卡片网格
- **暗色模式**：主题切换并自动记忆
- **Bing 每日背景**：可选的 Bing 每日图片背景，带版权标注
- **关闭动效**：swoosh 音效 + 彩带特效
- **统一卡片样式**：Not Grouped、Saved for Later、Bookmarks 视觉一致

### 隐私
- **100% 本地**：数据不会离开你的设备
- **纯 Chrome 扩展**：无服务端、无 Node.js、无 npm，加载扩展即可使用

---

## 手动安装

**1. 克隆仓库**

```bash
git clone https://github.com/arbing/tab-out.git
```

**2. 加载 Chrome 扩展**

1. 打开 Chrome，访问 `chrome://extensions`
2. 打开右上角的 **开发者模式** 开关
3. 点击 **加载已解压的扩展程序**
4. 选择仓库中的 `extension/` 目录

**3. 打开新标签页**

新标签页会显示 Tab Out。

---

## 工作原理

```
打开新标签页
  -> Tab Out 按域名（或 Chrome 标签组）展示当前所有标签
  -> Quick Access 与 Homepages 置顶
  -> 点击标签标题跳转
  -> 处理完的分组一键关闭（swoosh + 彩带）
  -> 用搜索栏过滤，或把标签收藏到稍后再看
```

所有逻辑都运行在 Chrome 扩展内部。无外部服务、无 API 调用、无数据上传。收藏的标签和个人配置保存在 `chrome.storage.local`。可选的 Bing 背景仅从 `bing.com` 拉取（已在 `host_permissions` 中声明）。

---

## 技术栈

| 分类     | 技术 |
|----------|------|
| 扩展     | Chrome Manifest V3 |
| 权限     | `tabs`、`activeTab`、`storage`、`bookmarks`、`favicon`、`tabGroups` |
| 存储     | `chrome.storage.local` |
| 音效     | Web Audio API（合成音，无音频文件） |
| 动画     | CSS 过渡 + JS 彩带粒子 |
| 背景图片 | Bing 每日图片（可选） |

---

## 许可证

MIT

---

原作者 [Zara](https://x.com/zarazhangrui) · 增强分支由 [ArBing](https://github.com/arbing) 维护
