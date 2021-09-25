# v-bind 和 v-for

## v-bind 动态绑定属性

在 data 中定义了一张图片，我们希望把这张图片渲染到页面上

```js
export default {
  data() {
    return {
      img: 'http://destiny001.gitee.io/image/monkey_02.jpg',
    };
  },
};
```

利用 v-bind 进行渲染

```html
<image v-bind:src="img"></image>
```

还可以缩写成:

```html
<image :src="img"></image>
```

## v-for 的使用

data 中定以一个数组，最终将数组渲染到页面上

```js
data () {
  return {
    arr: [
      { name: '刘能', age: 29 },
      { name: '赵四', age: 39 },
      { name: '宋小宝', age: 49 },
      { name: '小沈阳', age: 59 }
    ]
  }
}
```

利用 v-for 进行循环

```js
<view v-for="(item,i) in arr" :key="i">名字：{{item.name}}---年龄：{{item.age}}</view>
```
