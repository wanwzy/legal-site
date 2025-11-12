# 法律文件网站部署指南

本文档介绍如何将法律文件网站部署到 **GitHub Pages** 和 **Vercel** 两种平台。

## 📁 项目结构

```
/legal-site
  /public
    index.html         # 首页，包含隐私政策和用户协议链接
    privacy.html       # 隐私政策页面
    terms.html         # 用户协议页面
  README.md            # 本部署指南
```

## 🔧 自定义配置

在使用前，请将以下占位符替换为您的实际信息：

- `[公司名称]` → 您的公司名称
- `[联系邮箱]` → 您的联系邮箱
- `[数据保留期]` → 数据保留天数（默认180天）
- `[隐私专员姓名]` → 隐私专员姓名
- `[联系电话]` → 联系电话
- `[统一社会信用代码]` → 统一社会信用代码
- `[注册地址]` → 公司注册地址
- `[办公地址]` → 公司办公地址

## 🚀 GitHub Pages 部署

### 步骤 1: 创建 GitHub 仓库

1. 登录 GitHub 并创建新仓库
2. 仓库名称建议：`legal-site` 或 `privacy-terms`
3. 设置为 Public（免费版 GitHub Pages 仅支持公共仓库）

### 步骤 2: 上传文件

1. 克隆仓库到本地：
   ```bash
   git clone https://github.com/your-username/legal-site.git
   cd legal-site
   ```

2. 将 `public` 文件夹中的所有文件复制到仓库根目录

3. 提交并推送：
   ```bash
   git add .
   git commit -m "Initial commit: Legal site files"
   git push origin main
   ```

### 步骤 3: 启用 GitHub Pages

1. 在仓库页面点击 "Settings" 标签
2. 滚动到 "Pages" 部分
3. Source 选择 "Deploy from a branch"
4. Branch 选择 "main" 和 "/ (root)"
5. 点击 "Save"

### 步骤 4: 访问网站

几分钟后，您的网站将通过以下地址访问：
```
https://your-username.github.io/legal-site/
```

## 🌐 Vercel 部署

### 方式一：通过 Vercel CLI（推荐）

#### 前提条件
- 安装 Node.js 16+ 
- 安装 Vercel CLI：`npm i -g vercel`

#### 部署步骤

1. **安装依赖**（如果有的话）：
   ```bash
   npm init -y
   ```

2. **登录 Vercel**：
   ```bash
   vercel login
   ```

3. **部署项目**：
   ```bash
   cd legal-site
   vercel --prod
   ```

4. **按照提示完成配置**：
   - Set up and deploy? `Y`
   - Which scope? 选择您的账户
   - Link to existing project? `N`
   - What's your project's name? `legal-site`
   - In which directory is your code located? `./`
   - Override settings? `N`

5. **获取访问链接**：
   部署完成后，Vercel 将显示类似信息：
   ```
   ✅  Production: https://legal-site-xxx.vercel.app [1m 23s]
   📝  Deployed to production. Run `vercel --prod` to overwrite later.
   💡  To change the domain, go to https://vercel.com/your-username/legal-site
   ```

### 方式二：通过 Vercel Web 界面

#### 步骤 1: 打包文件

将 `legal-site/public` 文件夹打包为 ZIP 文件

#### 步骤 2: 登录 Vercel

1. 访问 [vercel.com](https://vercel.com)
2. 使用 GitHub、GitLab 或邮箱登录

#### 步骤 3: 创建新项目

1. 点击 "New Project"
2. 选择 "Import from ZIP file"
3. 上传您的 ZIP 文件
4. 项目名称：`legal-site`
5. Framework Preset: 选择 "Other"
6. 点击 "Deploy"

#### 步骤 4: 配置构建设置（如需要）

如果 Vercel 询问构建设置：

- **Build Command**: 留空（静态文件不需要构建）
- **Output Directory**: 留空（根目录就是输出目录）
- **Install Command**: 留空

### 方式三：通过 Git 仓库

#### 步骤 1: 推送代码到 Git 仓库

将代码推送到 GitHub、GitLab 或 Bitbucket

#### 步骤 2: 在 Vercel 中导入

1. 在 Vercel 控制台点击 "New Project"
2. 选择您的 Git 仓库
3. 配置项目：
   - Framework Preset: "Other"
   - Root Directory: 选择包含 HTML 文件的目录
4. 点击 "Deploy"

## ⚙️ 自定义域名（可选）

### GitHub Pages 自定义域名

1. **添加 CNAME 文件**：
   在仓库根目录创建 `CNAME` 文件，内容为您的域名：
   ```
   legal.yourdomain.com
   ```

2. **配置 DNS**：
   在您的域名服务商处添加 CNAME 记录：
   ```
   Type: CNAME
   Name: legal
   Value: your-username.github.io
   ```

3. **启用 HTTPS**：
   在 GitHub 仓库的 Pages 设置中，勾选 "Enforce HTTPS"

### Vercel 自定义域名

1. **在 Vercel 项目设置中添加域名**：
   - 进入项目 → Settings → Domains
   - 添加您的自定义域名

2. **配置 DNS**：
   根据 Vercel 提供的 DNS 配置信息设置

## 📝 维护和更新

### 更新法律文件内容

1. 修改对应的 HTML 文件（privacy.html 或 terms.html）
2. 确保更新文件中的日期信息
3. 重新部署到相应平台

### 版本控制建议

建议使用 Git 进行版本控制，每次更新时：

```bash
git add .
git commit -m "Update privacy policy - 2025-11-12"
git push origin main
```

## 🔒 安全和合规建议

1. **定期更新**：建议每季度检查一次法律文件内容
2. **版本存档**：保留历史版本的备份，以便审计
3. **法律咨询**：重大变更前建议咨询法律专家
4. **用户通知**：重要变更时通过邮件等方式通知用户

## 📞 技术支持

如果在部署过程中遇到问题：

- **GitHub Pages**：查看 [GitHub Pages 官方文档](https://docs.github.com/en/pages)
- **Vercel**：查看 [Vercel 官方文档](https://vercel.com/docs)
- **通用问题**：检查浏览器控制台错误信息

## 📄 许可证

本项目采用 MIT 许可证，详情请查看 LICENSE 文件。

---

**最后更新**：2025年11月12日  
**维护者**：[您的名称或团队]  
**联系方式**：[联系邮箱]
