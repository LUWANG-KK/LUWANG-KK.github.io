# 个人网站

Hugo + [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 主题，部署在 GitHub Pages。

## 写一篇新文章

```
hugo new content posts/我的标题.md
```

文件生成在 `content/posts/`，打开它：

- 把 `draft: true` 改成 `draft: false`（否则不会发布）
- `title` 是显示的标题，文件名会变成网址的一部分（建议用英文或拼音，例如 `posts/on-writing.md`）
- `categories` / `tags` 可填可不填
- `summary` 是首页列表里显示的一句话摘要

正文用 Markdown 写。

## 本地预览

```
hugo server -D
```

浏览器打开 http://localhost:1313 ，改文件会自动刷新。`-D` 表示连草稿一起看。

## 发布

```
git add -A && git commit -m "新文章" && git push
```

推到 GitHub 后，`.github/workflows/hugo.yml` 会自动构建并部署，大约一两分钟后网站更新。

## 目录说明

| 路径 | 作用 |
| --- | --- |
| `hugo.yaml` | 站点配置：标题、菜单、社交链接、首页介绍 |
| `content/posts/` | 所有文章 |
| `content/about.md` | 「关于」页 |
| `content/archives.md` `content/search.md` | 归档页和搜索页（内容为空，靠模板生成） |
| `static/` | 图片等静态文件，放这里后用 `/图片名.png` 引用 |
| `themes/PaperMod` | 主题，git submodule，不要手改 |
| `public/` | 构建产物，已被 git 忽略 |

## 改主题设置

常改的都在 `hugo.yaml` 的 `params` 下：`homeInfoParams` 是首页那段自我介绍，`socialIcons` 是首页下方的图标，`menu.main` 是顶部导航。
更多选项见 [PaperMod 文档](https://github.com/adityatelange/hugo-PaperMod/wiki/Features)。
