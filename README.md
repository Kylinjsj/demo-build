# demo-build

用来测试 GitHub Pages 部署的最小示例。

## 内容

- `index.html` —— 唯一的页面，纯静态
- `.nojekyll` —— 空文件，关掉 GitHub 默认的 Jekyll 处理

没有构建步骤，没有依赖，`git push` 后 GitHub 直接发布。

## 部署设置

仓库 `Settings` → `Pages`：

- Source：`Deploy from a branch`
- Branch：`main`
- 目录：`/ (root)`

发布地址：`https://kylinjsj.github.io/demo-build/`

## 几个要点

- `Deploy from a branch` 只能选 `/` 或 `/docs`，不能自定义成 `public`、`dist` 这类目录名
- 仓库必须是 public，Pages 才能免费使用
- GitHub Pages 只发静态文件，没有函数运行时，不能像 Cloudflare Pages 那样写 `functions/api/xxx.js`
- 首页文件名必须是 `index.html`（或 `index.md`），否则根路径会 404

## 和 Cloudflare Pages 的对比

| | GitHub Pages | Cloudflare Pages |
|---|---|---|
| 静态文件 | ✅ | ✅ |
| 后端接口 | ❌ | ✅ `functions/` |
| 环境变量 / 密钥 | ❌ | ✅ |
| KV / D1 等绑定 | ❌ | ✅ |
| 自定义目录名 | ❌ 只能 `/` 或 `/docs` | ✅ 任意子目录 |
