# Zhihao Xu — Personal Website

一个轻量的 Quarto 个人网站，用于发布完整实验博客和维护作品列表。

## 本地预览

安装 [Quarto](https://quarto.org/docs/get-started/)，然后运行：

```bash
quarto preview
```

完整构建：

```bash
quarto render
```

生成结果位于 `_site/`。

## 新增博客

复制文章模板：

```bash
cp -r templates/research-note posts/my-new-note
```

然后编辑 `posts/my-new-note/index.qmd`：

1. 修改标题、摘要、日期和分类。
2. 将 `draft: true` 改为 `draft: false` 或删除该行。
3. 把图、表和视频放在文章目录中，使用相对路径引用。
4. 运行 `quarto preview` 检查页面。

如果文章执行 Python/R/Julia 代码，请先在本地运行：

```bash
quarto render posts/my-new-note/index.qmd
```

这会更新 `_freeze/`，应将它和文章一起提交。

## 更新作品

直接编辑 `works.qmd`。在作品数量较少时，手工维护比引入额外数据管线更清晰；论文多起来后再迁移到 BibTeX。

## GitHub Pages 部署

1. 在 GitHub 创建公开仓库 `xuzhihaoup.github.io`。
2. 将本目录内容推送到仓库的 `main` 分支。
3. 打开 **Settings → Pages → Build and deployment**。
4. 将 **Source** 设为 **GitHub Actions**。

之后每次推送到 `main`，`.github/workflows/publish.yml` 都会自动构建并部署网站。

默认地址：<https://xuzhihaoup.github.io>
