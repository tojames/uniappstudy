# 发送请求

## 网络请求

在 uni 中可以调用 uni.request 方法进行请求网络请求

需要注意的是：在小程序中网络相关的 API 在使用前需要配置域名白名单。

**发送 get 请求**
**发送 post 请求**

- 示例

```html
<template>
  <view>
    <button @click="sendGet">发送请求</button>
  </view>
</template>
<script>
  export default {
  	methods: {
  		sendGet () {
  			uni.request({
  				url: 'http://localhost:8082/api/getlunbo',
          data: 请求的参数,
          header:设置请求的头部,header中不能设置Referer
          method:'GET', //GET捉着POST
          dataType:'json' //如果设置为json,会尝试对返回的数据做一次JSON.parse
  				success(res) {
  					console.log(res)
  				},
          fail(res){
            console.log(res)
          }
  			})
  		}
  	}
  }
</script>
```
