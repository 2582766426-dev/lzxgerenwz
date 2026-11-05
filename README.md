# 柳智熙作品集 — 2026-11-06 修正版

本包是完整网站源码与图片。已修复 pnpm-workspace.yaml 缺少 packages 的问题。

## 部署到 Cloudflare Workers

解压后，将文件夹内的源码上传到 GitHub 仓库根目录，覆盖旧版同名文件。不要仅上传 ZIP，也不要让 package.json 藏在第二层文件夹里。

在 Cloudflare 创建 Workers 项目并连接仓库（不是 Pages）。

- Worker 名称：liuzhixi-portfolio
- 生产分支：main
- 根目录：仓库根目录，保持默认
- 构建命令：pnpm run build
- 部署命令：pnpm exec wrangler deploy --config dist/server/wrangler.json --name liuzhixi-portfolio

正确的设置页面有“部署命令”，而不是只有“构建输出目录”。部署成功后访问 Cloudflare 提供的 workers.dev 地址。原 pages.dev 地址不会自动更新。

## 本地运行

使用 Node.js 22.13 或以上版本及 pnpm 10。

    pnpm install --frozen-lockfile
    pnpm run dev

## 本地构建与部署

    pnpm run build
    pnpm exec wrangler login
    pnpm exec wrangler deploy --config dist/server/wrangler.json --name liuzhixi-portfolio

包内不包含账号凭证、node_modules、Git 历史、构建缓存或原 Sites 项目绑定。图片和页面沿用当前最新版。