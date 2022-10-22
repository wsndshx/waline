---
title: 客户端提供的文件版本
---

Waline 提供多个版本的文件.

<!-- more -->

- `dist/waline.js`: 完整版本，UMD 格式

  此文件为 CDN 引入 `@waline/client` 的默认文件，53 KB Gzip 大小

- `dist/shim.mjs`: 不含依赖捆绑的完整版本， ES Module 格式

  此文件为 `import` 引入 `@waline/client` 的默认文件, 19.39 KB Gzip 大小

- `dist/shim.cjs`: 不含依赖捆绑的完整版本，Common JS 格式

  此文件为 `require` 引入 `@waline/client` 的默认文件，19.59 KB Gzip 大小

- `dist/waline.css`: Waline CSS 样式

- `dist/waline-meta.css`: Waline Meta 图标 CSS

- `dist/component.mjs`: Waline 的 Vue 组件，ES Module 格式，不含依赖捆绑

  此文件用于在 Vue 项目中以组件模式使用 Waline 评论, 18.28 KB Gzip 大小

- `dist/comment.js`: Waline 的评论数模块，UMD 格式， < 1KB Gzip 大小

  此文件用于 CDN 引入，用于仅需页面评论数的情况

- `dist/pageview.js`: Waline 的浏览量模块，UMD 格式， < 1KB Gzip 大小

  此文件用于 CDN 引入，用于仅需页面浏览量的情况

其他格式文件:

- `dist/waline.cjs`: `dist/waline.js` 文件的 Common JS 格式

- `dist/waline.mjs`: `dist/waline.js` 文件的 ES Module 格式

- `dist/comment.cjs`: `dist/comment.js` 文件的 Common JS 格式

- `dist/comment.mjs`: `dist/comment.js` 文件的 ES Module 格式

- `dist/pageview.cjs`: `dist/pageview.js` 文件的 Common JS 格式

- `dist/pageview.mjs`: `dist/pageview.js` 文件的 ES Module 格式
