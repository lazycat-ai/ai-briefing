# AI 日报 GitHub Pages 部署指南

## 一次性设置（5 分钟）

### 1. 在 GitHub 上创建仓库

打开 https://github.com/new ，创建一个新仓库：
- 仓库名：`ai-briefing`（或你喜欢的名字）
- 设为 **Public**（GitHub Pages 免费版需要公开仓库）
- 不要勾选 "Add a README"

### 2. 在电脑上初始化并推送

打开终端，`cd` 到这个 `ai-briefing-site` 文件夹，然后执行：

```bash
cd ai-briefing-site
git init
git add .
git commit -m "初始化 AI 日报站点"
git branch -M main
git remote add origin https://github.com/你的用户名/ai-briefing.git
git push -u origin main
```

### 3. 开启 GitHub Pages

1. 打开仓库页面 → Settings → Pages
2. Source 选择 **Deploy from a branch**
3. Branch 选择 **main**，文件夹选 **/ (root)**
4. 点击 Save

等 1-2 分钟，你的日报就上线了：
**https://你的用户名.github.io/ai-briefing/**

---

## 每日更新流程

每天生成新的日报后，只需要：

```bash
# 1. 把新的 HTML 文件放到 briefings/ 文件夹
cp ai-briefing-2026-04-18.html ai-briefing-site/briefings/2026-04-18.html

# 2. 更新 index.html（在历史日报区域新增一个卡片）

# 3. 推送
cd ai-briefing-site
git add .
git commit -m "添加 2026-04-18 日报"
git push
```

推送后 1-2 分钟自动生效，新链接：
**https://你的用户名.github.io/ai-briefing/briefings/2026-04-18.html**

---

## 分享方式

- **Dchat / 微信群**：直接发 H5 链接，点开即看
- **微信公众号**：文章里放简报摘要，"阅读原文"链接指向 H5 页面
- **给老板**：发微信纯文本版 + H5 链接

## 文件结构

```
ai-briefing-site/
├── index.html              ← 日报首页（历史列表）
├── briefings/
│   ├── 2026-04-17.html     ← 每日 H5 日报
│   ├── 2026-04-18.html
│   └── ...
├── SETUP.md                ← 本文件
└── .nojekyll               ← 告诉 GitHub 不要用 Jekyll 处理
```
