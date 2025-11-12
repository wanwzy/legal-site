# Vercel 部署说明

## 🚀 Vercel 部署方法

### 方法一：使用 Vercel CLI（推荐）

如果您已登录 Vercel：

```bash
cd legal-site
vercel --prod
```
https://api.minimaxi.com/v1
### 方法二：Web 界面部署

1. 访问 [vercel.com](https://vercel.com) 并登录
2. 点击 "New Project"
3. 选择 "Import from ZIP file"
4. 上传 `legal-site-deploy.zip` 文件
5. 项目名称：`legal-site`
6. Framework Preset: `Other`
7. 点击 "Deploy"

### 方法三：Git 仓库部署

1. 将代码推送到 GitHub/GitLab
2. 在 Vercel 中选择 "Import Git Repository"
3. 选择您的仓库进行部署

## 📁 部署文件说明

本项目是纯静态网站，包含以下文件：
- `index.html` - 首页
- `privacy.html` - 隐私政策
- `terms.html` - 用户协议

## 🌍 部署后访问地址

部署成功后，Vercel 将提供如下格式的访问地址：
```
https://your-project-name.vercel.app
```

具体地址以 Vercel 部署完成后的显示为准。

## 💡 本地预览

部署前可以本地预览：

```bash
# 使用 Python 简单服务器
cd legal-site
python -m http.server 8000

# 或使用 Node.js 的 serve
npx serve .
```

然后访问：`http://localhost:8000`

## 🔧 自定义域名（如需要）

在 Vercel 项目设置中的 "Domains" 部分添加您的自定义域名。

---
*最后更新：2025年11月12日*
