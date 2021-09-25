# 上拉加载

通过在 pages.json 文件中找到当前页面的 pages 节点下 style 中配置 onReachBottomDistance 可以设置距离底部开启加载的距离，默认为 50px

通过 onReachBottom 监听到触底的行为

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
        arr: ['前端', 'java', 'ui', '大数据', '前端', 'java', 'ui', '大数据'],
      };
    },
    onReachBottom() {
      console.log('触底了');
    },
  };
</script>

<style>
  view {
    height: 100px;
    line-height: 100px;
  }
</style>
```
