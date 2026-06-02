# Understanding-the-Linux-Virtual-Memory-Manager-zh

由 LLM 协助完成的《Understanding the Linux Virtual Memory Manager》（作者 Mel Gorman）中文翻译项目。基于 Linux 内核 2.4.22，并对 2.6 做了介绍。

## 目录结构

- `original_html/` — 原书英文 HTML 源文件（`understand001.html` 至 `understand029.html`、样式表 `understand.css` 以及 `figures/` 插图目录）。
- `translated_html/` — 翻译后的中文 HTML 文件（`understand0XX_zh.html`）以及对应的样式表 `understand_zh.css`。
- `index.html` — 项目入口页面。
- `AGENTS.md` — AI 代理协作时遵循的工作规则。

## 使用方式

在浏览器中打开 `original_html/index.html` 阅读英文原版，或打开 `translated_html/index.html` 阅读中文翻译版本。

## 翻译进度

全部完成：

- 前置内容：目录、代码注释目录、前言。
- 正文 14 章：第 1 章〈引言〉至第 14 章〈结语〉。
- 代码注释附录 A–K：附录 A〈引言〉至附录 K〈交换管理〉。
- 全部插图均已替换为带中文标注的内联 `<svg>`，原始 PNG 图保留在 `original_html/figures/` 仅作参考。

源文件 `understand029.html` 在原书中为空，已跳过。
