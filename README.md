# Wu Luchen

你好，我是 **Wu Luchen**，哈尔滨工程大学计算机科学与技术专业本科二年级学生。我的兴趣集中在人工智能与大语言模型，目前在 **Yu Zhiwen 教授的实验室**参与研究，主要关注 **LLM 推理加速**。

- **2025.9**：进入哈尔滨工程大学学习。
- **2025–2026**：获得 Xiaomi Scholarship（计算机学院前 2 名）。
- **2026.8**：参加 NTU Artificial Intelligence Special Camp。
- **2026.5 至今**：担任 HEU AIGC Club 主席，参与组织 Red Leaf Festival、Sci-Tech Innovation Carnival 等校园活动。

[个人主页](https://xiluii.github.io/) · [GitHub](https://github.com/xiluii) · [ORCID](https://orcid.org/0009-0007-5242-5261) · [Email](mailto:xiluii@hrbeu.edu.cn)

## 个人信息在哪里修改

这个仓库用于维护我的个人主页。站点基于 Jekyll 和 Academic Pages，目前只保留首页与 404 错误页，使用浅色模式和 Times New Roman 字体，已移除其他分页和底部页脚卡片。

| 要更新的内容 | 文件 | 修改位置 |
| --- | --- | --- |
| 首页自我介绍、研究方向、教育经历、奖学金、交流活动、社团经历 | [`_pages/about.md`](_pages/about.md) | 文件顶部的配置之后，直接编辑 Markdown 正文 |
| 首页大标题 | [`_pages/about.md`](_pages/about.md) | 顶部的 `title` |
| 顶部站点名称 | [`_config.yml`](_config.yml) | 顶层的 `title` |
| 个人姓名与网站简介 | [`_config.yml`](_config.yml) | 顶层的 `name`、`description`，以及 `author.name` |
| 侧栏所在地、邮箱、GitHub、ORCID 等链接 | [`_config.yml`](_config.yml) | `author` 下的 `location`、`email`、`github`、`orcid` 等字段 |
| 头像 | [`images/头像.png`](images/头像.png) 与 [`_config.yml`](_config.yml) | 替换图片，或修改 `author.avatar` 指向的新文件名 |
| 简历、论文等附件 | [`files/`](files/) | 添加文件，再在首页正文中插入下载链接 |
| 仓库首页的自我介绍与维护说明 | [`README.md`](README.md) | 本文件；与网站正文分别维护 |

### 修改首页正文

打开 `_pages/about.md`，保留文件最前面的配置块与 `permalink: /`，在配置块之后修改介绍和各个栏目。新增一条经历时，可沿用现有格式：

```markdown
## Educations

- **[2025.9]** Be admitted to Harbin Engineering University
```

首页支持普通 Markdown：`##` 表示栏目标题，`-` 表示列表，`**文字**` 表示加粗，`[文字](链接)` 表示链接。新增栏目也直接写在此文件中。

### 修改侧栏信息和头像

打开 `_config.yml`，在 `author:` 下修改对应字段。`github` 填用户名，`orcid` 等链接字段填完整 URL；不需要展示的字段可以留空。YAML 使用空格缩进，修改时保持原有层级。

头像的本地文件放在 `images/` 中。目前实际使用的是 `images/头像.png`，可以用新图片替换这个文件；如果改用另一个文件名，需要同时修改：

```yaml
author:
  avatar: "profile.png"
```

上面的示例对应 `images/profile.png`，配置中只填写文件名。仅替换 `files/头像.png` 不会更新侧栏头像。

站点地址配置目前为 `url: https://xiluii.github.io`、`repository: xiluii/xiluii.github.io`，`baseurl` 留空。日常更新个人信息时保留这些值。

### 添加附件

例如，将简历上传为 `files/cv.pdf`，再在 `_pages/about.md` 中添加：

```markdown
[Download my CV](/files/cv.pdf)
```

更新姓名、身份、研究方向或联系方式时，也同步修改 README 开头的介绍和链接，保持网站与仓库说明一致。

## 更新和发布流程

### 方法一：直接在 GitHub 上修改

适合只更新文字、联系方式或少量图片的情况，无需安装本地开发环境。

1. 打开 [仓库](https://github.com/xiluii/xiluii.github.io)，确认当前分支为 `master`。
2. 找到需要修改的文件，例如 `_pages/about.md` 或 `_config.yml`，点击编辑按钮并修改内容；图片和附件可通过 **Add file → Upload files** 上传。
3. 查看修改内容，填写提交说明并提交到 `master`。如果同一次更新涉及多个文件，逐个完成并保持内容一致。
4. 打开 [Actions](https://github.com/xiluii/xiluii.github.io/actions)，等待 **pages build and deployment** 显示成功。
5. 打开 [个人主页](https://xiluii.github.io/)，检查文字、头像和链接。若仍显示旧内容，强制刷新页面。

### 方法二：本地修改后推送

**1. 获取最新版本。** 在仓库目录中运行：

```bash
git status
git pull --ff-only
```

先确认没有未处理的本地修改，再拉取远程版本。如果尚未下载仓库，可以先运行：

```bash
git clone git@github.com:xiluii/xiluii.github.io.git
cd xiluii.github.io
```

**2. 编辑文件。** 根据前面的表格更新首页正文、侧栏信息、头像或附件；涉及自我介绍时同步更新 README。

**3. 本地预览与构建检查。** 仅修改 README 时可以跳过此步骤。环境需要 Ruby、Bundler；本项目使用 Ruby 3.2 进行过构建验证。Windows 可以在 WSL 中运行以下命令。首次使用时，在仓库目录安装依赖：

```bash
bundle config set --local path vendor/bundle
bundle install
```

启动预览：

```bash
bundle exec jekyll serve --config _config.yml,_config_docker.yml --host 127.0.0.1
```

打开 [本地预览](http://127.0.0.1:4000/)，检查首页和手机宽度下的布局。这里同时加载 `_config_docker.yml`，使预览使用本地资源。修改 `_config.yml` 后，需要停止并重新启动服务。

发布前运行一次构建检查：

```bash
bundle exec jekyll build --strict_front_matter
```

只更新文字、图片或 SCSS 时，不需要重建 JavaScript；如果修改了 `assets/js/_main.js`、`assets/js/theme.js` 或导航脚本，则先运行以下命令，并将生成的 `assets/js/main.min.js` 一并提交：

```bash
npm install
npm run build:js
```

**4. 检查改动、提交并推送。** 下面以更新介绍和配置为例，只暂存本次实际修改的文件：

```bash
git diff
git add _pages/about.md _config.yml README.md
git diff --cached
git diff --cached --check
git commit -m "Update personal information"
git push
```

如果更新了头像、附件或样式，提交前也需要用 `git add` 暂存相应文件，例如 `git add "images/头像.png"`。`_site/`、`node_modules/`、`vendor/` 和本地缓存已被忽略，不需要提交。

本地当前分支为 `master`，已经设置了远程跟踪，因此使用 `git pull --ff-only` 和 `git push` 即可。这份本地检出的远程名称为 `master`，通过 `git clone` 新下载的仓库通常为 `origin`；可用 `git remote -v` 查看，更新流程不依赖固定的远程名称。

**5. 确认线上发布。** 等待 [Actions](https://github.com/xiluii/xiluii.github.io/actions) 中本次提交的 **pages build and deployment** 成功，再访问 [个人主页](https://xiluii.github.io/) 检查结果。推送成功表示代码已上传，发布成功后网站才会显示新版。

## 维护说明

- 首页与 README 的自我介绍是两份独立内容，更新个人信息时需要同步维护。
- 当前站点保持单页结构，新增经历直接写入 `_pages/about.md`。
- 字体设置位于 `_sass/_themes.scss`，页面布局位于 `_layouts/`，主样式入口为 `assets/css/main.scss`。
- README 通过 `_config.yml` 排除在网站输出之外，仅作为 GitHub 仓库说明展示。
- 如果构建失败，打开 Actions 中失败的任务查看日志，修正对应文件后重新提交。

本网站基于 [Academic Pages](https://github.com/academicpages/academicpages.github.io) 模板，保留原项目的 [LICENSE](LICENSE)。
