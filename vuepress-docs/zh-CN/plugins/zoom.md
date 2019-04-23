# zoom

## 介绍

zoom 插件为 better scroll 增加缩放的功能。

## 使用

为了开启缩放功能，你需要首先引入 zoom 插件，并通过全局方法 `BScroll.use()` 使用

```js
import BScroll from 'BScroll'
import Zoom from 'zoom'

BScroll.use(Zoom)
```

上面步骤完成后，在 Better Scroll 的基础能力上扩展了缩放的功能，但是想要缩放真正生效，还需要在 `options` 中传入正确的配置：

```js
new BScroll('.bs-wrap', {
  freeScroll: true,
  scrollX: true,
  scrollY: true,
  useTransition: true,
  zoom: {
    start: 1,
    min: 0.5,
    max: 2
  }
})
```

以下是和缩放功能相关的配置：
- zoom

  开启 zoom 功能。若没有这只该项，则插件不会生效。该配置同时也是用来设置 zoom 特性的相关配置，具体请参考[zoom配置](./zoom.html#zoom-配置)。

- freeScroll

  如果希望当放大之后，当前区域在 x 和 y 轴方向都可以滚动时，必须设置为 `true`。同时需要设置 scrollX 和 scrollY 均为 true。

- scrollX

  如果希望当放大之后，当前区域在 x 轴方向可以滚动时，必须设置为 `true`。

- scrollY

  如果希望当放大之后，当前区域在 y 轴方向可以滚动时，必须设置为 `true`。

<demo qrcode-url="zoom/">
  <template slot="code-template">
    <<< @/example/vue/demo/zoom/default.vue?template
  </template>
  <template slot="code-script">
    <<< @/example/vue/demo/zoom/default.vue?script
  </template>
  <template slot="code-style">
    <<< @/example/vue/demo/zoom/default.vue?style
  </template>
  <zoom-default slot="demo"></zoom-default>
</demo>

## zoom 配置
|名称|类型|描述|默认值|例子|
|----------|:-----:|:-----------|:--------:|:-------|
|start|number|开始的缩放时的基础比例|-|start:1 // 开始缩放时当前尺寸为1|
|min|number|最小缩放比例|-|min:0.5|
|max|number|最大缩放比例|-|max:2|

## api

### zoomTo(scale, x, y)

将滚动体缩放到指定的大小。

**参数**

|名称|类型|描述|
|----------|:-----:|:-----------|
|scale|number|缩放大小|
|x|number|缩放原点的横坐标, 相对于整个文档的左边距|
|y|number|缩放原点的纵坐标, 相对于整个文档的上边距|

**返回值**：无
