# scss 和字体图标

## uni-app 中的样式

- rpx 即响应式 px，一种根据屏幕宽度自适应的动态单位。以 750 宽的屏幕为基准，750rpx 恰好为屏幕宽度。屏幕变宽，rpx 实际显示效果会等比放大。

- 使用`@import`语句可以导入外联样式表，`@import`后跟需要导入的外联样式表的相对路径，用`;`表示语句结束

- 支持基本常用的选择器 class、id、element 等

- 在 `uni-app` 中不能使用 `*` 选择器。

- `page` 相当于 `body` 节点

- 定义在 App.vue 中的样式为全局样式，作用于每一个页面。在 pages 目录下 的 vue 文件中定义的样式为局部样式，只作用在对应的页面，并会覆盖 App.vue 中相同的选择器。

- `uni-app` 支持使用字体图标，使用方式与普通 `web` 项目相同，需要注意以下几点：

  - 字体文件小于 40kb，`uni-app` 会自动将其转化为 base64 格式；

  - 字体文件大于等于 40kb， 需开发者自己转换，否则使用将不生效；

  - 字体文件的引用路径推荐使用以 ~@ 开头的绝对路径。

    ```
     @font-face {
         font-family: test1-icon;
         src: url('~@/static/iconfont.ttf');
     }
    ```

- 使用图标

```bash
<view class="iconfont icon-名字"></view>
```

- 如何使用 scss 或者 less

点击 HbuilderX 里面的 工具--->插件安装-->scss/sass 编译 点击安装

- 使用的时候

```bash

<style lang="scss">
.box{
	.content{
		color:red;
		font-size: 48rpx;
	}
}
</style>
```
