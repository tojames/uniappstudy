# Text 组件的基本使用

## 组件的概念

uni-app 提供了丰富的基础组件给开发者，开发者可以像搭积木一样，组合各种组件拼接称自己的应用

uni-app 中的组件，就像 `HTML` 中的 `div` 、`p`、`span` 等标签的作用一样，用于搭建页面的基础结构

## text 文本组件的用法

### 001 - text 组件的属性

|    属性    |  类型   | 默认值 | 必填 |                      说明                      |
| :--------: | :-----: | :----: | :--: | :--------------------------------------------: |
| selectable | boolean | false  |  否  |                  文本是否可选                  |
|   space    | string  |   .    |  否  | 显示连续空格，可选参数：`ensp`、`emsp`、`nbsp` |
|   decode   | boolean | false  |  否  |                    是否解码                    |

- `text` 组件相当于行内标签、在同一行显示
- 除了文本节点以外的其他节点都无法长按选中

### 002 - 代码案例

```html
<view>
  <!-- 长按文本是否可选 -->
  <text selectable="true">来了老弟</text>
</view>

<view>
  <!-- 显示连续空格的方式 -->
  <view>
    <text space="ensp">来了 老弟</text>
  </view>
  <view>
    <text space="emsp">来了 老弟</text>
  </view>
  <view>
    <text space="nbsp">来了 老弟</text>
  </view>
</view>

<view>
  <text>skyblue</text>
</view>

<view>
  <!-- 是否解码 -->
  <text decode="true">&nbsp; &lt; &gt; &amp; &apos; &ensp; &emsp;</text>
</view>
```
