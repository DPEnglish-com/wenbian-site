# 问辩 官网静态站点

公开访问站点：**https://dpenglish-com.github.io/wenbian-site/**

- 纯静态产物，由 `wenbian` 私有仓库的 `apps/site` 构建（`pnpm build:site`）后发布到这里
- 不要在本仓库直接改页面：源码在私有仓库的 `packages/landing`，两处会不一致
- `downloads/` 放 Android 包；`provider-icons/` 是模型供应商标识

## 更新方式

```bash
# 在私有仓库里
pnpm build:site
cp -R apps/site/dist/. /path/to/wenbian-site/

# 在这里
git add -A && git commit -m "站点更新" && git push
```

`.nojekyll` 保留：关掉 Jekyll 处理，避免带下划线的目录/文件被吞掉。
