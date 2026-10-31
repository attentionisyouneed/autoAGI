# 占博 · 个人简历网站

一个用 **Vibe Coding** 方式搭建的单页个人简历站点 —— 纯原生 HTML / CSS / JavaScript，零框架、零构建、零运行时依赖。

**[在线预览](https://attentionisyouneed.github.io/autoAGI/)**

---

## 这是什么

武汉科技大学管理学院工商管理专业学生的个人简历网站。整个站点从视觉设计到交互动效都由 AI 辅助完成，也是一次「AI 协助实际交付」的小实验。

站点没有使用任何前端框架，也没有打包流程：样式、脚本和字体全部内联在 `index.html` 内部，图片按相对路径同目录引用；另外还提供了一个把图片也一并 base64 内联的完全离线版。

## 功能特性

**内容分区**

单页多段式结构：首页 / 核心亮点 / 经历 / 项目经历 / 技能矩阵 / 坦克大战 / 获奖与证书。

顶部导航采用 `tablist` 模式，除鼠标点击外还支持方向键切换，切换时焦点同步到对应标签。

**入口彩蛋**

首页是一道「Choose the Right Person · 选择正确的人」的选择题 —— 三个选项里只有一个能带你进入主站。

**内嵌小游戏：坦克大战 · 进阶版**

页面里藏了一个可以真正玩的坦克对战小游戏，用 Canvas 2D 手写实现：游戏循环、子弹发射与碰撞检测、WASD / 方向键操控。

**背景音乐**

进入站点后播放背景音乐，提供静音开关，不打扰阅读。

**滚动进场动画**

基于 `IntersectionObserver`，元素进入视口时才触发动画，避免无意义的全局动画损耗。

**玻璃拟态视觉**

大量使用 `backdrop-filter` 与分层模糊，在保证可读性的前提下做出通透的层次感。

**响应式与打印**

17 处媒体查询覆盖手机到桌面；`@media print` 单独适配了打印样式，页面上的打印按钮可一键输出成 PDF 简历。

**无障碍与可访问性**

63 处 `aria-*` 属性与语义化 `role` 标注，导航支持键盘操作，切换分区时焦点同步到对应标签。

**完全离线可用**

`index-standalone.html` 是把字体、图片、样式全部 base64 内联后的单文件版本（约 5.5 MB），拷贝到任何机器上双击即可打开，不需要网络。

## 技术栈

| 层面 | 选型 |
| --- | --- |
| 结构 | HTML5 语义化标签 |
| 样式 | 原生 CSS3（Flex / Grid / `backdrop-filter` / `@media`） |
| 交互 | Vanilla JavaScript（ES6+） |
| 图形 | Canvas 2D + `requestAnimationFrame` |
| 动画 | `IntersectionObserver` + CSS `transition` / `transform` |
| 音频 | `<audio>` 元素 + `muted` 状态管理 |
| 部署 | GitHub Pages（Jekyll 构建工作流） |

没有 React、没有 Vue、没有构建工具，也没有 npm 依赖 —— 所有代码都直接写在这两个 HTML 文件里。

## 目录结构

```
autoAGI/
├── index.html              # 主站，单文件（内联样式、脚本、字体）
├── index-standalone.html   # 完全自包含的离线版（约 5.5 MB）
├── avatar.jpg              # 头像
├── cover.jpg               # 封面
├── finale.jpg              # 结局画面
├── bg.jpg                  # 背景
├── game-cover.jpg          # 游戏封面
├── tile-1.jpg ~ tile-9.jpg # 配图素材
├── musk.jpg                # 配图素材
├── bgm.mp3                 # 背景音乐
├── credentials/            # 证书与凭证（含说明文件）
└── .github/workflows/      # GitHub Pages 部署工作流
```

## 本地运行

不需要安装任何依赖。

**方式一：直接打开**

双击 `index.html`。

**方式二：起一个本地服务器**（推荐，避免部分浏览器的本地文件限制）

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000`。

## 部署

站点托管在 GitHub Pages 上，由 `.github/workflows/jekyll-gh-pages.yml` 在推送到 `main` 分支时自动构建发布。

如果要部署到自己的账号：Fork 本仓库 → 在 Settings → Pages 里把 Source 设为 GitHub Actions（或直接使用 `main` 分支根目录）→ 推送即生效。

## 关于 Vibe Coding

这个项目的代码绝大部分由 AI 生成，我负责的是判断与取舍：想要什么样的视觉、信息怎么组织、哪个动画值得留、哪里的交互是多余的。

过程中最花时间的不是写代码，而是**把模糊的感觉描述成可执行的指令**，以及在 AI 给出方案后判断它是否真的解决了问题。这也是我认为 AI 时代更重要的能力 —— 不是记住语法，而是知道自己要什么。

## 联系

- GitHub：[@attentionisyouneed](https://github.com/attentionisyouneed)
- 邮箱：attentionisaIIyouneed@outlook.com

---

<sub>本站最后更新于 2026.08 · 由纯 HTML / CSS / JS 构建</sub>
