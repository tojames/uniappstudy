# 数据缓存

## **uni.setStorage**

[官方文档](https://uniapp.dcloud.io/api/storage/storage?id=setstorage)

将数据存储在本地缓存中指定的 key 中，会覆盖掉原来该 key 对应的内容，这是一个异步接口。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="setStor">存储数据</button>
  </view>
</template>

<script>
  export default {
    methods: {
      setStor() {
        uni.setStorage({
          key: 'id',
          data: 100,
          success() {
            console.log('存储成功');
          },
        });
      },
    },
  };
</script>

<style></style>
```

## uni.setStorageSync

将 data 存储在本地缓存中指定的 key 中，会覆盖掉原来该 key 对应的内容，这是一个同步接口。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="setStor">存储数据</button>
  </view>
</template>

<script>
  export default {
    methods: {
      setStor() {
        uni.setStorageSync('id', 100);
      },
    },
  };
</script>

<style></style>
```

## uni.getStorage

从本地缓存中异步获取指定 key 对应的内容。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="getStorage">获取数据</button>
  </view>
</template>
<script>
  export default {
    data() {
      return {
        id: '',
      };
    },
    methods: {
      getStorage() {
        uni.getStorage({
          key: 'id',
          success: (res) => {
            this.id = res.data;
          },
        });
      },
    },
  };
</script>
```

## uni.getStorageSync

从本地缓存中同步获取指定 key 对应的内容。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="getStorage">获取数据</button>
  </view>
</template>
<script>
  export default {
    methods: {
      getStorage() {
        const id = uni.getStorageSync('id');
        console.log(id);
      },
    },
  };
</script>
```

## uni.removeStorage

从本地缓存中异步移除指定 key。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="removeStorage">删除数据</button>
  </view>
</template>
<script>
  export default {
    methods: {
      removeStorage() {
        uni.removeStorage({
          key: 'id',
          success: function () {
            console.log('删除成功');
          },
        });
      },
    },
  };
</script>
```

## uni.removeStorageSync

从本地缓存中同步移除指定 key。

代码演示

```html
<template>
  <view>
    <button type="primary" @click="removeStorage">删除数据</button>
  </view>
</template>
<script>
  export default {
    methods: {
      removeStorage() {
        uni.removeStorageSync('id');
      },
    },
  };
</script>
```
