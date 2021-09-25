# uniui 的使用

[uni-ui 文档](https://uniapp.dcloud.io/component/README?id=uniui)

1、进入 Grid 宫格组件

2、使用 HBuilderX 导入该组件

3、导入该组件

```html
import uniGrid from "@/components/uni-grid/uni-grid.vue" import uniGridItem from
"@/components/uni-grid-item/uni-grid-item.vue"
```

4、注册组件

```html
components: {uniGrid,uniGridItem}
```

5、使用组件

```html
<uni-grid :column="3">
  <uni-grid-item>
    <text class="text">文本</text>
  </uni-grid-item>
  <uni-grid-item>
    <text class="text">文本</text>
  </uni-grid-item>
  <uni-grid-item>
    <text class="text">文本</text>
  </uni-grid-item>
</uni-grid>
```
