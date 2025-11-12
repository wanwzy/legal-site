# 淘宝上下文服务 - 法律文档站点

一个纯静态的法律文档网站，包含隐私政策和用户协议页面。

## 📁 项目结构

```
/legal-site
  /public
    index.html                # 首页 - 列出隐私政策和用户协议
    privacy.html              # 隐私政策（12节，含退出/删除/数据导出）
    terms.html                # 用户协议（计费、SLA、试用退订、责任限制）
  README.md                   # 部署指南
  package.json                # 项目配置
  vercel.json                 # Vercel 部署配置
  .github/workflows/          # GitHub Actions 配置
    deploy-gh-pages-simple.yml  # GitHub Pages 自动部署
```

## 🚀 部署方法

### 方法一：GitHub Pages

#### 手动部署
1. 将项目代码推送到 GitHub 仓库
2. 在仓库 **Settings** 中找到 **Pages** 选项
3. 在 **Source** 部分选择：
   - 分支：`main`
   - 目录：`/public`
4. 点击 **Save**，GitHub Pages 会自动部署您的站点

#### 自动部署（推荐）
1. 将项目代码推送到 GitHub 仓库的 `main` 分支
2. 仓库已包含 GitHub Actions 工作流文件 `.github/workflows/deploy-gh-pages-simple.yml`
3. GitHub Actions 会自动检测代码推送并部署到 GitHub Pages
4. 在仓库 **Actions** 标签页中可以查看部署状态

访问地址格式：`https://[username].github.io/[repository-name]/`

---

### 方法二：Vercel

#### 1. ZIP 上传部署
1. 访问 [vercel.com](https://vercel.com) 并登录
2. 点击 **New Project**
3. 选择 **Import from ZIP file**
4. 上传项目根目录下的 `legal-site-deploy.zip` 文件
5. 项目名称：`legal-site`（或自定义）
6. Framework Preset: `Other`
7. 点击 **Deploy**

#### 2. Git 仓库部署
1. 将项目代码推送到 GitHub/GitLab 仓库
2. 在 Vercel 中选择 **Import Git Repository**
3. 选择您的仓库并点击 **Import**
4. 配置项目名称和框架后点击 **Deploy**

#### 3. CLI 部署
```bash
# 安装 Vercel CLI
npm install -g vercel

# 登录 Vercel
vercel login

# 部署到生产环境
cd legal-site
vercel --prod
```

访问地址格式：`https://[project-name].vercel.app/`

---

## 📝 内容说明

### privacy.html（隐私政策）
- 共包含 12 节内容
- 包含数据收集、使用、共享、保护等完整内容
- 包含退出/删除/数据导出功能说明
- 使用 `<span class="placeholder">[占位符]</span>` 标记需要填充的字段
- 默认数据保留期：180天

### terms.html（用户协议）
- 包含计费条款
- 包含 SLA（服务级别协议）
- 包含试用与退订说明
- 包含责任限制条款
- 使用 `<span class="placeholder">[占位符]</span>` 标记需要填充的字段

## 🖥️ 本地运行

```bash
# 安装依赖（如果有）
npm install

# 启动本地服务器
npm run dev

# 或使用 Python 服务器
python -m http.server 8000
```

访问地址：`http://localhost:59335`（端口号可能不同）

## 📅 最后更新日期
2025年11月12日
