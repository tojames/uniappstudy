# Button 组件的使用

## button 按钮组件的用法

## 001 - 组件的属性

|  属性名  |  类型   | 默认值  |           说明            |
| :------: | :-----: | :-----: | :-----------------------: |
|   size   | String  | default |        按钮的大小         |
|   type   | String  | default |      按钮的样式类型       |
|  plain   | Boolean |  false  | 按钮是否镂空，背景色透明  |
| disabled | Boolean |  false  |         是否按钮          |
| loading  | Boolean |  false  | 名称是否带 loading t 图标 |

- `button` 组件默认独占一行，设置 `size` 为 `mini` 时可以在一行显示多个

## 002 - 案例代码

```html
<button size="mini" type="primary">前端</button>

<button size="mini" type="default" disabled="true">前端</button>

<button size="mini" type="warn" loading="true">前端</button>
```
