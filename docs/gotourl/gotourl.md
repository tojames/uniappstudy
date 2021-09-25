# uni 中的导航跳转

## 利用 navigator 进行跳转

navigator 详细文档：[文档地址](https://uniapp.dcloud.io/component/navigator)

跳转到普通页面

```html
<navigator url="/pages/about/about" hover-class="navigator-hover">
  <button type="default">跳转到关于页面</button>
</navigator>
```

跳转到 tabbar 页面

```html
<navigator url="/pages/message/message" open-type="switchTab">
  <button type="default">跳转到message页面</button>
</navigator>
```

## 利用编程式导航进行跳转

[导航跳转文档](<[uni.navigateTo](https://uniapp.dcloud.io/api/router?id=navigateto)>)

**利用 navigateTo 进行导航跳转**

保留当前页面，跳转到应用内的某个页面，使用`uni.navigateBack`可以返回到原页面。

```html
<button type="primary" @click="goAbout">跳转到关于页面</button>
```

通过 navigateTo 方法进行跳转到普通页面

```js
goAbout () {
  uni.navigateTo({
    url: '/pages/about/about',
  })
}
```

**通过 switchTab 跳转到 tabbar 页面**

跳转到 tabbar 页面

```html
<button type="primary" @click="goMessage">跳转到message页面</button>
```

通过 switchTab 方法进行跳转

```js
goMessage () {
  uni.switchTab({
    url: '/pages/message/message'
  })
}
```

**redirectTo 进行跳转**

关闭当前页面，跳转到应用内的某个页面。

```html
<!-- template -->
<button type="primary" @click="goMessage">跳转到message页面</button>
<!-- js -->
goMessage () { uni.switchTab({ url: '/pages/message/message' }) }
```

通过 onUnload 测试当前组件确实卸载

```js
onUnload () {
  console.log('组件卸载了')
}
```

## 导航跳转传递参数

在导航进行跳转到下一个页面的同时，可以给下一个页面传递相应的参数，接收参数的页面可以通过 onLoad 生命周期进行接收

传递参数的页面

```js
goAbout () {
  uni.navigateTo({
    url: '/pages/about/about?id=80',
  });
}
```

接收参数的页面

```js
<script>
	export default {
		onLoad (options) {
			console.log(options)
		}
	}
</script>
```
