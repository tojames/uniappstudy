# 配置基本的 tabbar

## 配置 tabbar

如果应用是一个多 tab 应用，可以通过 tabBar 配置项指定 tab 栏的表现，以及 tab 切换时显示的对应页。

**Tips**

- 当设置 position 为 top 时，将不会显示 icon
- tabBar 中的 list 是一个数组，只能配置最少 2 个、最多 5 个 tab，tab 按数组的顺序排序。

**属性说明：**

| 属性            | 类型     | 必填 | 默认值 | 描述                                                     | 平台差异说明              |
| --------------- | -------- | ---- | ------ | -------------------------------------------------------- | ------------------------- |
| color           | HexColor | 是   |        | tab 上的文字默认颜色                                     |                           |
| selectedColor   | HexColor | 是   |        | tab 上的文字选中时的颜色                                 |                           |
| backgroundColor | HexColor | 是   |        | tab 的背景色                                             |                           |
| borderStyle     | String   | 否   | black  | tabbar 上边框的颜色，仅支持 black/white                  | App 2.3.4+ 支持其他颜色值 |
| list            | Array    | 是   |        | tab 的列表，详见 list 属性说明，最少 2 个、最多 5 个 tab |                           |
| position        | String   | 否   | bottom | 可选值 bottom、top                                       | top 值仅微信小程序支持    |

其中 list 接收一个数组，数组中的每个项都是一个对象，其属性值如下：

| 属性             | 类型   | 必填 | 说明                                                                                                                      |
| ---------------- | ------ | ---- | ------------------------------------------------------------------------------------------------------------------------- |
| pagePath         | String | 是   | 页面路径，必须在 pages 中先定义                                                                                           |
| text             | String | 是   | tab 上按钮文字，在 5+APP 和 H5 平台为非必填。例如中间可放一个没有文字的+号图标                                            |
| iconPath         | String | 否   | 图片路径，icon 大小限制为 40kb，建议尺寸为 81px \* 81px，当 postion 为 top 时，此参数无效，不支持网络图片，不支持字体图标 |
| selectedIconPath | String | 否   | 选中时的图片路径，icon 大小限制为 40kb，建议尺寸为 81px \* 81px ，当 postion 为 top 时，此参数无效                        |

案例代码：

```js
"tabBar": {
    "color":"#A0522D",
    "selectedColor":"#002266",
    "backgroundColor":"#FFD662",
		"list": [
			{
				"text": "首页",
				"pagePath":"pages/index/index",
				"iconPath":"static/tabs/home.png",
				"selectedIconPath":"static/tabs/home-active.png"
			},
			{
				"text": "信息",
				"pagePath":"pages/message/message",
				"iconPath":"static/tabs/message.png",
				"selectedIconPath":"static/tabs/message-active.png"
			},
			{
				"text": "我们",
				"pagePath":"pages/contact/contact",
				"iconPath":"static/tabs/contact.png",
				"selectedIconPath":"static/tabs/contact-active.png"
			}
		]
	}
```
