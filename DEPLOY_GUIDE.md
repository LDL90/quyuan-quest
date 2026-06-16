# 🚀 部署「寻找屈原的足迹」到 GitHub Pages — 完整教程

> 从零开始，一步一步来。即使你从未用过 GitHub，跟着做也能成功。

---

## 前置准备：安装工具

### 第1步：安装 Git

1. 打开浏览器，访问 https://git-scm.com/download/win
2. 点击 **"Click here to download"** 下载安装包（约50MB）
3. 双击安装包，一路点 **Next** 默认安装即可
4. 安装完成后，**重启电脑**（重要！）
5. 验证安装：打开 PowerShell，输入：
   ```
   git --version
   ```
   应显示类似 `git version 2.xx.x`

### 第2步：注册 GitHub 账号（如果还没有）

1. 访问 https://github.com/signup
2. 填写用户名、邮箱、密码
3. 完成验证邮件确认

---

## 部署流程

### 第3步：创建 GitHub 仓库

1. 登录 GitHub，点击右上角 **"+"** → **"New repository"**
2. 填写信息：
   - **Repository name**: `quyuan-quest`（或你喜欢的名字）
   - **Description**: `端午屈原主题公园探秘互动游戏`
   - **Public** ✅（必须选Public，GitHub Pages免费版只支持公开仓库）
   - ❌ 不要勾选 "Add a README file"（我们会自己上传）
   - ❌ 不要选 .gitignore 和 License
3. 点击 **"Create repository"**

### 第4步：上传项目文件

打开 PowerShell，依次执行以下命令：

```powershell
# 1. 进入项目目录
cd C:\Users\LDL\.qclaw\workspace\quyuan_park_quest

# 2. 初始化 Git 仓库
git init

# 3. 添加所有文件
git add .

# 4. 提交
git commit -m "端午屈原主题公园探秘游戏"

# 5. 关联远程仓库（把 YOUR_USERNAME 换成你的GitHub用户名）
git remote add origin https://github.com/YOUR_USERNAME/quyuan-quest.git

# 6. 推送到 GitHub
git branch -M main
git push -u origin main
```

> ⚠️ 第5步的 `YOUR_USERNAME` 要换成你的实际GitHub用户名！
> 
> 首次推送时Git会弹出登录窗口，输入你的GitHub账号密码即可。
> 
> 如果GitHub要求token认证（2021年后新政策），操作如下：
> - 去 https://github.com/settings/tokens → Generate new token (classic)
> - 勾选 `repo` 权限 → 生成token → 复制
> - 推送时密码栏填这个token（不是你的GitHub密码）

### 第5步：启用 GitHub Pages

1. 在仓库页面，点击 **"Settings"**（设置）
2. 左侧找到 **"Pages"**（在 Code & Automation 分类下）
3. 设置：
   - **Source**: 选择 **"Deploy from a branch"**
   - **Branch**: 选择 **"main"**，文件夹选 **"/ (root)"**
   - 点击 **"Save"**
4. 等待约1-3分钟，页面顶部会出现绿色提示：
   > ✅ Your site is published at https://YOUR_USERNAME.github.io/quyuan-quest/

### 第6步：验证网站

打开浏览器，访问：
```
https://YOUR_USERNAME.github.io/quyuan-quest/
```

应该能看到「寻找屈原的足迹」首页！🎉

---

## 生成二维码

### 第7步：为每个关卡生成二维码

每个关卡的URL格式：

| 关卡 | URL |
|------|-----|
| 首页（开始游戏） | `https://YOUR_USERNAME.github.io/quyuan-quest/` |
| 第1关 汨罗江畔 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level1` |
| 第2关 艾草飘香 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level2` |
| 第3关 龙舟竞渡 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level3` |
| 第4关 离骚长歌 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level4` |
| 第5关 粽香传情 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level5` |
| 第6关 屈原精神 | `https://YOUR_USERNAME.github.io/quyuan-quest/#level6` |

> ⚠️ 目前H5页面是按顺序闯关模式（从首页进入依次解锁），实际使用时只需扫描**首页一个二维码**即可。
> 如果你想做**每个关卡独立扫码**的模式（不用按顺序），我帮你改代码。

**推荐二维码生成工具：**

- 🇨🇳 **草料二维码**（推荐）: https://cli.im/ — 免费中文工具，支持批量生成
  - 输入URL → 生成二维码 → 可添加Logo/文字 → 下载打印
- 🌍 **QR Code Generator**: https://www.qr-code-generator.com/
- 🌍 **GoQR**: https://goqr.me/

**打印建议：**
- 每个二维码建议尺寸 **6×6cm** 以上（手机扫码需足够大）
- 可以做成**防水卡片**：打印后用透明自粘袋封装（约5元/包）
- 或者直接用**防水不干胶贴纸纸**打印（淘宝搜"防水不干胶"，约15元）

---

## 关卡卡片设计建议

每个关卡位置放一张卡片，包含：

```
┌──────────────────────┐
│  🏠 第1关 · 汨罗江畔   │
│                        │
│    ┌──────────┐        │
│    │  QR CODE │        │
│    │          │        │
│    └──────────┘        │
│                        │
│  扫码开始探秘 🐉        │
│  端午文化寻游           │
└──────────────────────┘
```

---

## 更新内容（后续修改）

如果踩点后需要修改关卡内容：

```powershell
# 1. 编辑文件（我帮你改，或你自己改）
# 2. 重新提交推送
cd C:\Users\LDL\.qclaw\workspace\quyuan_park_quest
git add .
git commit -m "更新关卡内容"
git push
```

推送后 GitHub Pages 约1-3分钟自动更新。

---

## 常见问题

| 问题 | 解决 |
|------|------|
| 推送时提示"Authentication failed" | 用Personal Access Token代替密码，见第4步说明 |
| 网站显示404 | 检查仓库是否Public，Pages是否启用，等几分钟再试 |
| 网页样式不对 | 检查 index.html 是否正确上传到仓库根目录 |
| 二维码扫不出来 | 增大二维码尺寸，确保打印清晰 |
| 手机上拍照功能不工作 | 需用HTTPS（GitHub Pages默认就是HTTPS，没问题） |
| 想修改关卡内容 | 告诉我，我帮你改代码后重新推送 |

---

## 一句话总结

**安装Git → 注册GitHub → 创建仓库 → git push → 启用Pages → 生成二维码 → 打印 → 开玩 🐉**

有任何步骤卡住了，随时告诉我，我帮你远程操作！