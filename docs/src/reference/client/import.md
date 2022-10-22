---
title: 客户端文件
icon: import
---

Waline 提供多种版本的客户端文件。你可以通过多种方式引入 Waline。

<!-- more -->

## 通过 NPM

### 安装

Waline 客户端已通过 `@waline/client` 发布到 [npm](https://www.npmjs.com/package/@waline/client)，你可以通过以下命令安装:

::: code-tabs#shell

@tab pnpm

```bash
pnpm add -D @waline/client
```

@tab yarn

```bash
yarn add -D @waline/client
```

@tab npm

```bash
npm i -D @waline/client
```

:::

### 使用

你可以通过多种形式导入需要的文件并使用，以下是一个示例。

::: code-tabs#lang

@tab JS

```js
import { init } from '@waline/client';

import '@waline/client/dist/waline.css';

init({
  el: '#waline',
  // ...
});
```

@tab TS

```ts
import { init } from '@waline/client';

import '@waline/client/dist/waline.css';

init({
  el: '#waline',
  // ...
});
```

:::
