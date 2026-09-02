# Yunpeng Li Academic Homepage

这是李运鹏个人学术主页的 GitHub Pages 仓库，网站地址：

- English: https://liyunpeng19970428.github.io/
- 中文: https://liyunpeng19970428.github.io/zh/

本文件是维护说明，不会影响网页显示。`_config.yml` 已经把 `README.md` 加入 `exclude`，因此 GitHub Pages 构建网站时会忽略它。

## 日常维护看哪里

- 英文正文：`index.md`
  - 修改英文 `About Me`、`Research Interests`、`News`。
- 中文正文：`zh.md`
  - 修改中文 `个人简介`、`研究方向`、`最新动态`。
- 论文列表：`_data/publications.yml`
  - 中英文页面共用同一份论文数据。
  - 论文题名、作者、会议名、PDF、GitHub、Hugging Face、论文图片都在这里维护。
- 左侧个人信息和链接：`_config.yml`
  - 修改姓名、职称、单位、邮箱、Google Scholar、OpenReview、ORCID、头像等。
- 论文图片和头像：`assets/img/`
  - 论文图片建议使用清晰的 PNG。
  - 当前论文缩略图展示比例为 16:9。
- 论文列表模板：`_includes/publications.md`
  - 一般不用改，除非要调整论文卡片显示哪些按钮。

## 中英文页面如何同步

论文列表只需要维护一份：`_data/publications.yml`。

英文首页 `/` 和中文页 `/zh/` 都会读取这一份论文数据，所以新增、删除或修改论文后，两边会同时更新。

需要分别维护的是页面正文：

- 英文介绍和英文新闻：改 `index.md`
- 中文介绍和中文新闻：改 `zh.md`

## 添加一篇论文

打开 `_data/publications.yml`，复制一篇已有论文条目，然后改成新论文信息。例如：

```yml
  - title: "Paper Title Here"
    authors: First Author, <strong>Yunpeng Li</strong>, Other Author
    conference_short: ACL
    conference: Annual Meeting of the Association for Computational Linguistics <strong>(ACL)</strong>, 2026.
    pdf: https://example.com/paper.pdf
    page: https://example.com/
    image: /assets/img/paper-name.png
    notes: Poster
```

如果有 GitHub 或 Hugging Face 链接，可以继续添加：

```yml
    github: https://github.com/xxx/yyy
    huggingface: https://huggingface.co/xxx/yyy
```

字段说明：

- `title`: 论文标题。中文页也保持英文，不需要翻译。
- `authors`: 作者列表。可以用 `<strong>Yunpeng Li</strong>` 加粗本人姓名。
- `conference_short`: 左上角的小标签，例如 `ACL`、`NeurIPS`、`WWW`。
- `conference`: 完整会议或期刊信息。
- `pdf`: PDF 链接。页面会显示 `PDF` 按钮。
- `page`: 论文主页或 OpenReview / ACL Anthology 页面。目前页面不显示 `Page` 按钮，但可以保留作为数据记录。
- `image`: 论文缩略图路径。图片应放在 `assets/img/` 下，并使用 `/assets/img/xxx.png` 这种路径。
- `notes`: 只有写 `Poster` 或 `Oral` 时，页面才会额外显示该标记。
- `github`: 可选。有则显示 `GitHub` 按钮。
- `huggingface`: 可选。有则显示 `Hugging Face` 按钮。

## 添加论文图片

1. 把图片上传到 `assets/img/`。
2. 文件名建议简洁，例如 `paper-new-work.png`。
3. 在 `_data/publications.yml` 里写：

```yml
    image: /assets/img/paper-new-work.png
```

建议图片比例接近 16:9，或者至少不要太窄太长。当前页面会把图片显示为统一的论文缩略图。

## 修改新闻

英文新闻在 `index.md`：

```md
- **[2026]** Our paper **XXX** was accepted by ACL 2026.
```

中文新闻在 `zh.md`：

```md
- **[2026]** 论文 **XXX** 被 ACL 2026 接收。
```

新闻不是自动翻译的。如果希望中英文新闻一致，需要在两个文件里各写一条。

## 修改个人简介和研究方向

英文页面改 `index.md`：

- `## About Me`
- `## Research Interests`
- `## News`

中文页面改 `zh.md`：

- `## 个人简介`
- `## 研究方向`
- `## 最新动态`

## 修改左侧栏信息

打开 `_config.yml`，常用字段包括：

```yml
title: Yunpeng Li
position: Associate Professor
affiliation: Institute of Information Engineering, Chinese Academy of Sciences
email: liyunpeng (at) iie.ac.cn
google_scholar: https://scholar.google.com/citations?hl=en&user=CDyIJocAAAAJ
openreview: https://openreview.net/profile?id=~Yunpeng_Li7
orcid: https://orcid.org/0000-0002-5156-889X
acl_anthology: https://aclanthology.org/people/yunpeng-li/
```

中文页左侧显示的中文姓名、中文职称和中文单位在 `zh.md` 的顶部：

```yml
profile_name: 李运鹏
profile_position: 副研究员
profile_affiliation: 中国科学院信息工程研究所
```

## 直接在 GitHub 网页上修改

如果直接在 GitHub 上编辑文件，不需要手动运行命令部署。

步骤：

1. 打开仓库：https://github.com/liyunpeng19970428/liyunpeng19970428.github.io
2. 找到要修改的文件，例如 `_data/publications.yml`、`index.md`、`zh.md`。
3. 点击右上角编辑按钮。
4. 修改内容。
5. 点击 `Commit changes`。
6. 确认提交到 `main` 分支。
7. 等几十秒到两分钟，GitHub Pages 会自动重新构建网站。

更新后访问：

- https://liyunpeng19970428.github.io/
- https://liyunpeng19970428.github.io/zh/

## 在本地修改并发布

如果在本地电脑上修改，提交和发布流程是：

```powershell
cd "C:\Users\lumin\Documents\New project"
git status
git add .
git commit -m "Update homepage"
git push origin main
```

推送到 `main` 后，GitHub Pages 会自动部署。

## 本地预览

本地预览需要 Ruby 和 Bundler：

```bash
bundle install
bundle exec jekyll serve
```

然后打开：

```text
http://localhost:4000/
```

如果本机没有 Ruby / Bundler，也可以直接提交到 GitHub，等 GitHub Pages 构建完成后在线检查。

## Attribution

This site is adapted from [Minimal Light](https://github.com/yaoyao-liu/minimal-light), which is licensed under CC0-1.0.
