---
title: Compatible with historical versions of Emoji
---

This guide will show you how to work with Valine, as well as older versions of Valine.

## Compatible with Valine

Valine provides a legacy version that is compatible with Valine's emoji options.

In legacy version, you can use `emojiCDN` to set emoji image link prefix, and use `emojiMaps` to set the mapping between emoji title and image.

```html
<!-- Use Legacy version compatible with Valine and Waline V1 clients -->
<script src="https://unpkg.com/@waline/client@v2/dist/legacy.umd.js"></script>
<script>
  Waline({
    el: '#waline',
    serverURL: '<YOUR SERVER URL>',

    // Set up CDN, such as Weibo emoticon CDN
    emojiCDN: 'https://img.t.sinajs.cn/t4/appstyle/expression/ext/normal/',
    // emoticon title and image map
    emojiMaps: {
      smile: 'e3/2018new_weixioa02_org.png',
      lovely: '09/2018new_keai_org.png',
      // ... more expressions
    },
  });
</script>
```

## Historical style issues

In the historical version, since the HTML tags will be escaped, the Emoji image completely uses the Markdown image syntax, which causes the historical version of the Emoji to be rendered by the pure `<img>` tag. If you use HD emojis, there may be display size issues.

Since `@waline/client@0.16.0`, we have successfully fixed the emoji size by improving the rendering method of Markdown.

If you need to adapt the emoji size of comments posted before this version, you can do so using CSS selectors:

```css
/* You need to replace `https://img.t.sinajs.cn` with your own CDN */
.wl-content img[src^="https://img.t.sinajs.cn"]
{
  width: 1.25em;
  margin: 0.25em;
  vertical-align: middle;
}
```
