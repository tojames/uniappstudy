# 图片的上传和预览

## 上传图片

uni.chooseImage 方法从本地相册选择图片或使用相机拍照。

案例代码

```html
<template>
  <view>
    <button @click="chooseImg" type="primary">上传图片</button>
    <view>
      <image v-for="item in imgArr" :src="item" :key="index"></image>
    </view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        imgArr: [],
      };
    },
    methods: {
      chooseImg() {
        uni.chooseImage({
          count: 1,
          success: (res) => {
            this.imgArr = res.tempFilePaths;
          },
        });
      },
    },
  };
</script>
```

## 预览图片

结构

```html
<view>
  <image
    v-for="item in imgArr"
    :src="item"
    @click="previewImg(item)"
    :key="item"
  ></image>
</view>
```

预览图片的方法

```js
previewImg (current) {
  uni.previewImage({
    urls: this.imgArr,
    current
  })
}
```
