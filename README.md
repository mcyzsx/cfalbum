# cfalbum

简短说明
- **项目类型**: Cloudflare Workers 项目
- **源码位置**: `src/index.js`
- **配置文件**: `wrangler.toml`

## 项目简介
这是一个基于 Cloudflare Workers + R2 + KV 的轻量项目，提供图片上传、展示和管理功能。它利用 Cloudflare 的边缘网络，实现快速的图片加载和处理。


## 先决条件
- Node.js（建议 16+）
- npm 或 pnpm
- Cloudflare 帐号
- `wrangler`（Cloudflare 官方 CLI）

如果尚未安装 `wrangler`：

```powershell
# 推荐使用 npx（无需全局安装）
npm install -g wrangler
# 或在每次运行时用 npx
# npx wrangler --version
```

## 管理 Secrets（环境变量）
对敏感信息使用 `wrangler secret`：

```powershell
npx wrangler secret put SECRET_NAME
```


## 部署到 Cloudflare
1. 确保 `wrangler.toml` 中配置了正确的 `account_id` 与 `name`。
2. 登录 Cloudflare（或确保 `CF_API_TOKEN` 已设好）：

```powershell
npx wrangler login
# 或在 CI 环境里设置 CF_API_TOKEN 环境变量
```

3. 发布：

```powershell
# 直接发布到 workers.dev 或配置的 route
npx wrangler deploy
# 若全局安装：
wrangler deploy
```

4. 发布成功后终端会返回部署的 URL，按需访问。
