# 部署指南

本文档介绍了如何将文章爬取工具部署到不同的平台，包括本地部署、Vercel部署和Cloudflare Pages部署。

## 本地部署

### 1. 克隆项目

```bash
git clone https://github.com/2066xll/article-crawler.git
cd article-crawler
```

### 2. 创建虚拟环境

```bash
python -m venv .venv
source .venv/bin/activate  # Linux/macOS
.venv\Scripts\activate  # Windows
```

### 3. 安装依赖

```bash
pip install -r requirements.txt
```

### 4. 运行应用

```bash
python app.py
```

### 5. 访问应用

在浏览器中访问 `http://127.0.0.1:5001`

## Vercel部署

### 1. 准备工作

- 确保您有一个GitHub账号
- 确保项目已经推送到GitHub

### 2. 部署步骤

1. 登录 [Vercel](https://vercel.com/)
2. 点击 "New Project"
3. 选择您的GitHub仓库
4. 配置部署选项：
   - Framework Preset: Python
   - Build Command: 留空
   - Output Directory: 留空
   - Install Command: `pip install -r requirements.txt`
5. 点击 "Deploy"

### 3. 访问应用

部署完成后，Vercel会为您分配一个域名，您可以通过该域名访问应用。

## Cloudflare Pages部署

### 1. 准备工作

- 确保您有一个GitHub账号
- 确保项目已经推送到GitHub
- 确保您有一个Cloudflare账号

### 2. 部署步骤

1. 登录 [Cloudflare Pages](https://pages.cloudflare.com/)
2. 点击 "Create a project"
3. 选择 "Connect to Git"
4. 选择您的GitHub仓库
5. 配置部署选项：
   - Build Command: 留空
   - Build Output Directory: `frontend`
6. 点击 "Save and Deploy"

### 3. 访问应用

部署完成后，Cloudflare Pages会为您分配一个域名，您可以通过该域名访问应用。

## 注意事项

1. **API部署**：Cloudflare Pages只支持静态站点部署，不支持Python后端。如果您需要完整的功能，包括爬取功能，建议将前端部署到Cloudflare Pages，后端部署到Vercel或其他支持Python的平台。

2. **环境变量**：如果您的应用需要环境变量，请在部署平台上配置相应的环境变量。

3. **域名配置**：您可以在部署平台上配置自定义域名，以便更好地访问您的应用。

4. **HTTPS**：所有部署平台都会自动为您的应用配置HTTPS，确保数据传输的安全性。

5. **更新部署**：当您更新GitHub仓库中的代码时，部署平台会自动重新部署您的应用。

## 故障排除

### 1. 部署失败

- 检查依赖是否正确安装
- 检查配置选项是否正确
- 查看部署日志，了解具体错误信息

### 2. 应用无法访问

- 检查应用是否成功部署
- 检查域名是否正确
- 检查网络连接

### 3. 功能无法使用

- 检查后端API是否正常运行
- 检查前端代码是否正确调用API
- 检查API URL是否正确配置

## 联系方式

如果您在部署过程中遇到问题，请随时提交Issue或联系项目维护者。