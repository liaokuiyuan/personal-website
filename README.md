# 廖奎源 · 个人网站

个人主页静态站点，单文件自包含（CSS / JS / 字体 / 图片全部内嵌为 base64），部署于 GitHub Pages。

**在线地址：** https://liaokuiyuan.github.io/

## 目录结构

| 文件 | 说明 |
| --- | --- |
| `index.html` | 站点全部内容（约 54.7 MB，自包含，无任何外部依赖） |
| `.nojekyll` | 跳过 GitHub Pages 的 Jekyll 构建，直接按静态文件发布 |
| `.gitattributes` | 关闭行尾转换（`* -text`），保证 `index.html` 字节级一致 |

## 本地预览

```powershell
# 进入仓库目录后任选一种
python -m http.server 8080
# 或
npx --yes serve -l 8080 .
```

浏览器打开 http://127.0.0.1:8080/ 即可。

## 发布方式

GitHub Pages 用户站点：仓库名为 `liaokuiyuan.github.io`，发布源为 `main` 分支根目录。
推送后 GitHub 会自动构建并发布，无需额外配置。

```powershell
git add -A
git commit -m "update site"
git push
```

## 说明

`index.html` 体积较大（54.7 MB），因为所有图片与字体都以 base64 内嵌以保证单文件可离线打开。
代价是**首次打开需要下载整个 54.7 MB**，移动网络下较慢。如需优化，可把内嵌资源抽成独立文件并
改为相对路径引用，或对图片做压缩/转 WebP。
