# 数据绑定

## uni-app 中的数据绑定(同 Vue)

在页面中需要定义数据，和我们之前的 vue 一摸一样，直接在 data 中定义数据即可

```js
export default {
  data() {
    return {
      msg: 'hello-uni',
    };
  },
};
```

## 插值表达式的使用

- 利用插值表达式渲染基本数据

  ```html
  <view>{{msg}}</view>
  ```

- 在插值表达式中使用三元运算

  ```html
  <view>{{ flag ? '我是真的':'我是假的' }}</view>
  ```

- 基本运算

  ```html
  <view>{{1+1}}</view>
  ```
