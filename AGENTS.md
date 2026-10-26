# AGENTS.md

Static HTML/CSS coursework site — no build step, no package manager, no tooling. Open files directly in a browser; there is nothing to install or run.

- Each `*.html` file is a self-contained lesson page; styles are inline in `<style>` blocks, except `css.css` which is linked by early lesson pages (1–4).
- Page filenames are Chinese lesson titles (e.g. `6-1 flex.html`); the `img/` folder holds referenced images — keep relative paths intact when moving files.
- No tests, lint, or typecheck exist. Verify changes by viewing the affected HTML in a browser.
- New `*.html` pages must be added as link-cards in `index.html` (update the works count in `.stats` too).
- 所有 JS 变量名、CSS 类名、HTML id 名必须以 `zhh_` 开头（如 `zhh_name`、`zhh_box`），新代码和重构时统一遵守。
- 新建 `*.html` 文件时必须在 `<body>` 开始标签后加入注释：`<!-- 姓名：张淮皓，建立时间：<建立日期>，使用的大模型：<模型名称>，功能名称：<页面功能> -->`。建立时间填实际日期，大模型填实际使用的模型名称（如 GLM-5.3-Flash），功能名称填该页功能（如「JavaScript 弹窗交互」）。
- 只使用原生 HTML/CSS/JavaScript 实现，不引入任何第三方库和 CDN（jQuery、Bootstrap、Lucide、Font Awesome 等一律不用）。
- 图标统一使用 `font/` 目录下的 iconfont 图标：页面 `<head>` 中链接 `font/iconfont.css`，用 `<span class="iconfont">&#xe6xx;</span>` 或对应图标类名的方式使用，可用图标清单见 `font/demo_index.html`。
- 需要服务器端数据时用原生 `fetch` 获取；注意 `fetch` 仅在 `http://` 下可用，直接双击以 `file://` 打开页面会被浏览器拦截，预览需启动本地静态服务器。
