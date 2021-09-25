# 下拉刷新

## 开启下拉刷新

在 uni-app 中有两种方式开启下拉刷新

- 需要在 `pages.json` 里，找到的当前页面的 pages 节点，并在 `style` 选项中开启 `enablePullDownRefresh`
- 通过调用 uni.startPullDownRefresh 方法来开启下拉刷新

## 通过配置文件开启

创建 list 页面进行演示

```html
<template>
  <view>
    杭州学科
    <view v-for="(item,index) in arr" :key="index"> {{item}} </view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        arr: ['前端', 'java', 'ui', '大数据'],
      };
    },
  };
</script>

<style></style>
```

通过 pages.json 文件中找到当前页面的 pages 节点，并在 `style` 选项中开启 `enablePullDownRefresh`

```js
{
  "path":"pages/list/list",
    "style":{
      "enablePullDownRefresh": true
    }
}
```

## 通过 API 开启

[api 文档](https://uniapp.dcloud.io/api/ui/pulldown)

```html
uni.startPullDownRefresh()
```

## 监听下拉刷新

通过 onPullDownRefresh 可以监听到下拉刷新的动作

```js
export default {
  data() {
    return {
      arr: ['前端', 'java', 'ui', '大数据'],
    };
  },
  methods: {
    startPull() {
      uni.startPullDownRefresh();
    },
  },
  onPullDownRefresh() {
    console.log('触发下拉刷新了');
  },
};
```

## 关闭下拉刷新

uni.stopPullDownRefresh()

停止当前页面下拉刷新。

案例演示

```html
<template>
  <view>
    <button type="primary" @click="startPull">开启下拉刷新</button>
    杭州学科
    <view v-for="(item,index) in arr" :key="index"> {{item}} </view>
  </view>
</template>
<script>
  export default {
    data() {
      return {
        arr: ['前端', 'java', 'ui', '大数据'],
      };
    },
    methods: {
      startPull() {
        uni.startPullDownRefresh();
      },
    },

    onPullDownRefresh() {
      this.arr = [];
      setTimeout(() => {
        this.arr = ['前端', 'java', 'ui', '大数据'];
        uni.stopPullDownRefresh();
      }, 1000);
    },
  };
</script>
```
