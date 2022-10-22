---
title: 自定义表情
icon: emoji
redirectFrom: /guide/client/emoji.html
---

你可以通过设置 `emoji` 选项自定义评论输入框的表情，你应该将它设置为包含*预设地址*或*预设配置对象*的**数组**。如果你不需要它，只需将它设置为 `false`。

<!-- more -->

## 预设

Waline 提供了一系列开箱即用的表情预设。你可以直接将它们添加到 `emoji` 选项中:

- Alus

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/alus
  ```

- 哔哩哔哩

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/bilibili
  ```

- 哔哩哔哩小黄脸

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/bmoji
  ```

- QQ

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/qq
  ```

- 贴吧

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/tieba
  ```

- Twitter Emoji

  - 表情:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-emoji
    ```

  ::: details 其他可用预设

  - 完整: (不推荐使用)

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw
    ```

  - 身体:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-body
    ```

  - 食物:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-food
    ```

  - 自然:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-natural
    ```

  - 对象:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-object
    ```

  - 符号:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-symbol
    ```

  - 人物:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-people
    ```

  - 运动:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-sport
    ```

  - 时间:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-time
    ```

  - 旅行:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-travel
    ```

  - 天气:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-weather
    ```

  - 旗帜:

    ```http
    https://unpkg.com/@waline/emojis@1.1.0/tw-flag
    ```

  :::

- 微博

  ```http
  https://unpkg.com/@waline/emojis@1.1.0/weibo
  ```

::: warning

Waline 不含有上述 Emoji 表情的任何版权，你需要自行承担使用风险。

:::

### 例子

```html
<div id="waline"></div>
<script type="module">
  import { init } from 'https://unpkg.com/@waline/client@v2/dist/waline.mjs';

  init({
    el: '#waline',
    serverURL: '<YOUR SERVER URL>',

    // 设置 emoji 为微博与哔哩哔哩
    emoji: [
      '//unpkg.com/@waline/emojis@1.1.0/weibo',
      '//unpkg.com/@waline/emojis@1.1.0/bilibili',
    ],
  });
</script>
```

## 创建自己的预设

除了 Waline 提供的预设外，你可以创建自己的预设。

你需要将所有表情图片放置在一个可以访问的服务器文件夹上，之后在根目录创建 `info.json`，并设置如下选项:

- `name`: Emoji 名称

- `prefix` (可选的): Emoji 图片名称的通用前缀

  ::: tip 推荐

  当你设置了多个 Emoji 选项卡时，我们推荐你为同一个选项卡内的所有表情图片添加一个共用前缀，以防与其他 Emoji 缩写相冲突。

  :::

- `type` (可选的): 图片的类型，会用作图片的后缀名

  ::: tip

  表情包应该是一套相同大小相同文件格式的图片。如果你的确需要使用不同类型的图片，请将此项留空并在之后的两个选项中手动指定后缀名。

  :::

- `icon`: 选项卡包含的图标的图片名 (要求同 `items`)

- `items`: 数组，每项是图片不包含通用前缀的文件名 (不含扩展名)

  ::: tip

  数组的顺序既是表情排列的顺序。

  :::

::: tip 使用 GitHub 仓库

我们更推荐你将图片上传到一个 GitHub 仓库，并为你的改动添加标签。这样你可以通过 GitHub CDN 链接来创建对应格式的预设。

比如，你可以利用 [cdn.jsdelivr.net](https://www.jsdelivr.com/) ，其格式为 `https://cdn.jsdelivr.net/gh/user/repo@version/file`。

:::

::: tip 使用使用配置对象

除了在图片文件夹下创建 `info.json` 来创建预设，我们也允许直接在 `emoji` 选项中直接添加配置对象。

配置对象的格式和 `info.json` 只有一点不同: 你应当额外添加 `folder` 选项为图片文件夹 (不应包含尾随 `/`)，以便 Waline 可以找到你的表情包。

:::
