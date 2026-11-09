# Yuan Tao 学术主页：精简版

本版本按你上传的 `T4OYU4N.github.io-master.zip` 整理，继续使用 GitHub Pages / Jekyll 和 Markdown。
保留现有单页主页的内容与结构：顶部姓名、Research 和 Teaching 导航，左侧头像和个人信息，右侧简介、研究与教学。
不依赖 AcademicPages 完整主题、业务 JavaScript、外部图标字体或额外 Jekyll 插件。

## 日常只需要改哪几个文件

| 要更新的内容 | 文件 | 说明 |
| --- | --- | --- |
| 简介、研究方向、论文、教学、正文更新时间 | `_pages/about.md` | 所有正文集中在这一个文件；论文列表和教学不再维护两份。 |
| 姓名、简短身份、邮箱、Google Scholar、网站描述 | `_config.yml` | `email` 是真实邮件地址，`email_display` 是页面显示的混淆写法。 |
| 头像照片 | `images/yuan_picture.jpg` | 用自己的新照片替换同名文件即可；若改文件名，同时修改 `_config.yml` 中的 `author.avatar`。 |
| 顶部导航 | `_data/navigation.yml` | 当前只有 Research 与 Teaching。 |
| 字体、间距、头像显示宽度 | `assets/css/main.css` | 一般不需要改。 |

本次没有修改你的博士年级、论文状态、论文年份或教学学期。
正文仍使用上传版本中的 `fourth-year` 和 `Last updated: September, 2026.`；更新学术内容时再改这些文字。

## 头像已改为完整长方形

原来的椭圆来自 `_sass/layout/_sidebar.scss` 中的 `border-radius: 50%`，并非照片自身带椭圆。
精简版的相关样式位于 `assets/css/main.css`：

```css
.author__avatar img {
  display: block;
  width: 175px;
  max-width: 100%;
  height: auto;
  border: 1px solid var(--border);
  border-radius: 0;
  padding: 5px;
}
```

保留图片本身的宽高比，不做椭圆遮罩或 `object-fit: cover` 裁切。
压缩包中仍使用原站点的 `images/yuan_picture.jpg`，图像字节未修改，也没有采用此前生成式编辑的照片。
现有原图为 1280 × 1792；以后替换成 3:4 的抱臂照片也会自然显示为 3:4。
如果替换图片的尺寸不同，可同时更新 `_layouts/default.html` 里 `<img>` 的 `width`、`height` 为新图片像素尺寸，帮助浏览器在加载前预留正确空间；CSS 的 `height: auto` 会保持照片比例。

## 本次保留了什么

| 内容 | 处理结果 |
| --- | --- |
| 当前个人简介、教育背景和导师链接 | 保留。 |
| 两个研究方向 | 保留原文。 |
| 三篇 Preprints、两篇 Articles | 保留标题、作者、年份、期刊和原有链接。 |
| 独立论文页中的额外链接 | 两个 PDF 链接和 SIAM 论文的 arXiv 链接已合入首页。 |
| 五条 Teaching Assistant 经历 | 保留课程、教师和学期。 |
| Email 与 Google Scholar | 保留；邮件链接改为可用的 `mailto:yuantao@link.cuhk.edu.hk`。 |
| 当前头像和 favicon | 原文件保留。 |
| 原 MIT 许可 | 保留在 `LICENSE`。 |
| 基本网站功能 | 保留响应式布局、可访问导航、404、canonical、页面描述、Open Graph、robots 和只列首页的 sitemap。 |

这里的“有用”指当前主页实际需要，或对维护、兼容旧链接有明确作用。
旧个人照片等未引用资源不等于没有保存价值；它们仍在你上传的原 ZIP 中，只是不进入本次精简部署包。

## 移除了什么，以及为什么

| 原文件或目录 | 判断依据与处理 |
| --- | --- |
| `_publications/` | 四篇内容都是 `Paper Title Number ...` 等模板示例；你的真实论文写在首页和 `_pages/publications.md`。移除。 |
| `_teaching/` | 两条都是示例课程；真实教学记录已保留在首页。移除。 |
| `_talks/`、`_portfolio/` | 模板报告与作品集示例，没有发现当前使用的真实记录。移除。 |
| `_posts/`、`_drafts/` | 示例博客、未来日期博客及占位草稿。移除。 |
| `_pages/cv.md` | 内容是 GitHub University 等模板虚构履历，不是你的真实 CV。移除。 |
| `files/` | 六个 PDF 均为 Sample PDF / Slides 示例，未发现你的真实论文或简历 PDF。移除。 |
| `_pages/about_old20260907.txt` | 旧简介仍写 `third-year`，并保留 `permalink: /`，与正式首页存在输出冲突风险。移除。 |
| `publications_old.html`、`teaching_old.html` | 停用的旧模板页面。移除。 |
| 原 `_pages/publications.md`、`_pages/teaching.md` | 真实但与首页重复；有用内容合入首页，旧地址保留跳转。 |
| 教程、Markdown 演示、archive、portfolio、talkmap 等 `_pages` 页面 | 服务于本次已移除的模板功能。移除。 |
| `_pages/terms.md` | 通用模板中关于评论、广告及分析工具的文字不对应当前站点。移除。 |
| `_data/comments/`、`_data/authors.yml`、`_data/ui-text.yml` | 示例评论、多作者和主题多语言配置；最小布局没有这些依赖。移除。 |
| `_includes/`、绝大多数 `_layouts/`、整个 `_sass/` | 主题组件已由一个实际使用的主页布局、一个跳转布局和一个 CSS 替代。 |
| `assets/js/`、`package.json` | 当前内容无需灯箱、视频适配、折叠组件和 jQuery；导航、布局直接由 HTML/CSS 实现。移除。 |
| 两套图标字体及其 CSS | 仅使用少量内联 SVG 图标，移除字体包。 |
| 模板全局加载的 MathJax 和 polyfill | 当前正文没有数学公式，无需加载。移除。 |
| `images/` 中其他文件 | 演示图片、主题截图和当前未引用的旧照片；部署包仅保留头像与 favicon。 |
| `markdown_generator/`、`talkmap/`、地图脚本和 notebooks | 当前真实内容不使用批量示例生成或报告地图。移除。 |
| `.github/workflows/scrape_talks.yml` | 该工作流抓取报告地图，并非网站发布工作流。移除。 |
| `.github/ISSUE_TEMPLATE/`、`CONTRIBUTING.md`、原模板 README | 模板项目协作说明，替换为本维护说明。 |
| `Dockerfile`、`docker-compose.yaml`、`_config_docker.yml` | 当前直接由 GitHub Pages 构建，无需 Docker 辅助。移除。 |
| 空白社交账号、评论系统、分析工具和模板集合配置 | 当前不使用，已从 `_config.yml` 移除。 |
| RSS Feed 链接 | 当前没有真实博客内容，移除空/示例 Feed 入口。 |

原配置对多个示例集合启用了 `output: true`，还开启了 `future: true`。
因此“没放在导航里”并不代表这些内容不会生成；清理后可以减少示例论文、示例课程和虚构 CV 被直接访问或索引的机会。

## 最终文件结构

总计 19 个文件，包含网站源码、必要资源与维护说明。

| 路径 | 用途 |
| --- | --- |
| `_config.yml` | 最小 Jekyll 配置和个人信息。 |
| `_data/navigation.yml` | 两个顶部导航链接。 |
| `_pages/about.md` | 唯一学术正文。 |
| `_layouts/default.html` | 页面 HTML、个人信息侧栏和页脚。 |
| `assets/css/main.css` | 唯一 CSS。 |
| `images/yuan_picture.jpg` | 当前头像。 |
| `images/favicon.svg` | 浏览器标签图标。 |
| `_layouts/redirect.html` | 简单 HTML 跳转模板，无插件依赖。 |
| `_pages/about-redirect.html` | `/about/` → `/`。 |
| `_pages/about-html-redirect.html` | `/about.html` → `/`。 |
| `_pages/publications-redirect.html` | `/publications/` → `/#publications`。 |
| `_pages/teaching-redirect.html` | `/teaching/` → `/#teaching`。 |
| `404.html` | 未找到页面时的返回入口。 |
| `sitemap.xml` | 仅列当前首页，避免收录已删除示例页面。 |
| `robots.txt` | 告知搜索引擎 sitemap 地址。 |
| `Gemfile` | 可选本地 Jekyll 环境，使用 GitHub Pages 依赖集合。 |
| `.gitignore` | 排除本地构建产物。 |
| `LICENSE` | 原模板许可。 |
| `README.md` | 本说明；已排除在网站构建之外。 |

其中四个旧地址跳转文件是为了保留链接兼容性，不需要日常修改。

## 怎样替换现有仓库

这个 ZIP 是完整的精简替换版本，而不是只含修改文件的补丁。
**只上传并覆盖同名文件，旧的模板目录仍会留在仓库中，不能完成清理。**

1. 先保存现有仓库副本；原 ZIP 也可作为本次清理前的备份。
2. 解压新 ZIP，进入 `T4OYU4N.github.io-minimal` 文件夹。
3. 在你的本地 `T4OYU4N.github.io` 仓库中，用这 19 个文件组成的目录树替换原站点文件；保留 Git 管理目录 `.git`。
   `_data`、`_layouts`、`_pages`、`assets`、`images` 应整体替换为精简版内容，不能只合并新文件。
   原包中的 `_includes`、`_sass`、`_publications`、`_teaching`、`_talks`、`_portfolio`、`_posts`、`_drafts`、`files`、`markdown_generator`、`talkmap` 等已不需要。
4. 将上述文件直接放在发布源的根目录，不要把外层 `T4OYU4N.github.io-minimal` 文件夹也套进去。
5. 在 GitHub Desktop 或你平时使用的 Git 工具中检查变更列表，再提交并推送。
6. 在仓库的 `Settings → Pages` 中确认发布源。对本包，最直接的方式是 `Deploy from a branch`，选择存放这些文件的分支和 `/(root)`。
   分支名以你的仓库实际设置为准；本次原 ZIP 来自 `master`，但压缩包本身不能证明当前线上 Pages 设置。
7. 查看 Pages 构建结果，再检查首页、Research/Teaching 导航及旧地址跳转。

本包继续使用 Jekyll，因此不要添加 `.nojekyll`。
如果你的仓库在本次 ZIP 之后另增了实际发布工作流或自定义域名配置，请在替换前与当前仓库核对；本清理范围只依据本次上传的内容。
这里没有替你操作 GitHub 仓库或发布线上网站。

GitHub 官方说明：

- [GitHub Pages 与 Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll)
- [配置发布源](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## 本地预览与验证范围

在已安装 Ruby 和 Bundler 的电脑上，可在项目根目录执行：

```bash
bundle install
bundle exec jekyll serve
```

然后打开终端显示的本地网址。

本次已完成以下检查：

- 真实源码经过独立 Liquid/Markdown 渲染，8 个预期页面/文本输出均存在，没有未展开模板或重复输出路径。
- 首页、原独立论文页和教学页中的外部学术链接全部保留，Google Scholar 和真实邮件链接正确。
- 27 处内部资源或链接引用、10 处锚点引用均可解析。
- 根路径与带 `/test-prefix` 的配置都通过本地路径检查。
- 浏览器中检查了桌面布局，以及 320 px、390 px 宽度的嵌入视口；均无横向溢出，头像为完整矩形，导航与联系方式可见。
- 浏览器中实际访问四个旧地址，均跳转到正确首页或锚点；404 页的返回链接与 `noindex` 元信息正确。
- 当前头像文件与原 ZIP 中的文件逐字节相同。

本次整理环境没有 Ruby/Jekyll，因此没有实际运行 Jekyll 构建或完成 GitHub Pages 线上部署。
辅助预览使用 Python Liquid 与 MarkdownIt；它不等于 Ruby Liquid / kramdown，最终构建结果仍需以 GitHub Pages 为准。
未逐一联网核验外部论文与学校链接的可用性；这些链接来自你提供的源码。
