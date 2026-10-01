# 王乐舟 Lezhou Wang · 个人网站

纯静态网站，无需构建，直接部署到 GitHub Pages 即可。

```
网页部署/
├── index.html    页面本体（样式与脚本都已内联）
├── img/          15 张已压缩的 WebP 照片（约 2 MB）
├── .nojekyll     告诉 GitHub Pages 原样发布，不做 Jekyll 处理
└── README.md     本说明
```

## 用 GitHub Pages 发布

### 方式一：网页上传（不用命令行）

1. 登录 GitHub，点右上角 **+ → New repository**。
2. 仓库名建议填 `你的用户名.github.io`，这样网址就是 `https://你的用户名.github.io/`。
   用其他名字（如 `portfolio`）也可以，网址会变成 `https://你的用户名.github.io/portfolio/`。
3. 选 **Public**，点 **Create repository**。
4. 在新仓库页面点 **uploading an existing file**，把本文件夹里的 `index.html`、`img` 文件夹、`.nojekyll` 一起拖进去，点 **Commit changes**。
   （Windows 默认隐藏以 `.` 开头的文件；即使漏传 `.nojekyll`，这个网站也能正常显示。）
5. 进入仓库 **Settings → Pages**，Source 选 **Deploy from a branch**，Branch 选 `main`、目录 `/ (root)`，点 **Save**。
6. 等 1–2 分钟，页面顶部会显示网址。

### 方式二：命令行

在本文件夹里打开终端：

```bash
git init
git add .
git commit -m "Personal website"
git branch -M main
git remote add origin https://github.com/你的用户名/你的仓库名.git
git push -u origin main
```

然后同样在 **Settings → Pages** 里开启。

## 更新网站

源文件在 `Desktop/cv/site/`：编辑 `layout.html`（结构与样式）和 `app.js.html`（脚本），运行 `node build.js` 生成新的 `index.html`，再把它和 `img/` 复制到这里，重新上传或 `git push`。

## 说明

- **AI 原型在公开网站上运行于检索模式**：“问问 AI 版的我”按关键词返回预先写好的回答，术语翻译回放示例。实时生成只在 Claude 的 Artifact 页面里可用。
- **字体**从 Google Fonts 加载；在国内网络下可能较慢或加载不到，页面会自动退回系统字体（苹方 / 微软雅黑），排版不受影响。
- **公开即可见**：页面含邮箱和照片，合影中有同学与老师，发布前请确认他们同意。
- **社交分享预览图**：上线后可把 `index.html` 里 `og:image` 的 `img/portrait-lean.webp` 改成完整网址（如 `https://你的用户名.github.io/img/portrait-lean.webp`），微信 / LinkedIn 分享时才会显示封面。
