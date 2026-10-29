# 问辩 官网静态站点

公开访问站点：**https://dpenglish-com.github.io/wenbian-site/**

- 纯静态产物，由 `wenbian` 私有仓库的 `apps/site` 构建（`pnpm build:site`）后发布到这里
- 不要在本仓库直接改页面：源码在私有仓库的 `packages/landing`，两处会不一致
- 仓库根只放构建产物：`index.html`、`assets/`（打包后的 JS/CSS）、`favicon.svg`；`downloads/` 已清空并移除（旧 BYOK Android 内测包已下架，不再公开分发），本仓库也没有 `provider-icons/` 目录

## 更新方式

```bash
# 在私有仓库里
pnpm build:site
cp -R apps/site/dist/. /path/to/wenbian-site/

# 在这里
git add -A && git commit -m "站点更新" && git push
```

`.nojekyll` 保留：关掉 Jekyll 处理，避免带下划线的目录/文件被吞掉。
