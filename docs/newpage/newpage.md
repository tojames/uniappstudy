# 创建新的页面和页面配置

## 创建新的页面

右键 pages 新建页面,在选择默认模板

```html
<template>
  <view> 这是信息页面 </view>
</template>

<script></script>

<style></style>
```

## 通过 pages 来配置页面

| 属性  | 类型   | 默认值 | 描述                                                                                          |
| ----- | ------ | ------ | --------------------------------------------------------------------------------------------- |
| path  | String |        | 配置页面路径                                                                                  |
| style | Object |        | 配置页面窗口表现，配置项参考 [pageStyle](https://uniapp.dcloud.io/collocation/pages?id=style) |

pages 数组数组中第一项表示应用启动页

```html
"pages": [ 、 { "path":"pages/home/home" }, { "path": "pages/index/index",
"style": { "navigationBarTitleText": "home" } } ]
```

通过 style 修改页面的标题和导航栏背景色，并且设置 h5 下拉刷新的特有样式

```js
"pages": [ //pages数组中第一项表示应用启动页，参考：https://uniapp.dcloud.io/collocation/pages
		{
			"path":"pages/message/message",
			"style": {
				"navigationBarBackgroundColor": "#007AFF",
        "navigationBarTitleText": "Home页面",
				"navigationBarTextStyle": "white",
				"enablePullDownRefresh": true,
				"disableScroll": true,
				"h5": {
					"pullToRefresh": {
						"color": "#007AFF"
					}
				}
			}
		}
	]
```
