# 组件之间的通讯方式

## 父组件给子组件传值

通过 props 来接受外界传递到组件内部的值

```html
<template>
  <view> 这是一个自定义组件 {{msg}} </view>
</template>

<script>
  export default {
    props: ['msg'],
  };
</script>

<style></style>
```

其他组件在使用 login 组件的时候传递值

```html
<template>
  <view>
    <test :msg="msg"></test>
  </view>
</template>

<script>
  import test from '@/components/test/test.vue';
  export default {
    data() {
      return {
        msg: 'hello',
      };
    },

    components: { test },
  };
</script>
```

## 子组件给父组件传值

通过$emit 触发事件进行传递参数

```html
<template>
  <view>
    这是一个自定义组件 {{msg}}
    <button type="primary" @click="sendMsg">给父组件传值</button>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        status: '打篮球',
      };
    },
    props: {
      msg: {
        type: String,
        value: '',
      },
    },
    methods: {
      sendMsg() {
        this.$emit('myEvent', this.status);
      },
    },
  };
</script>
```

父组件定义自定义事件并接收参数

```html
<template>
  <view>
    <test :msg="msg" @myEvent="getMsg"></test>
  </view>
</template>
<script>
  import test from '@/components/test/test.vue';
  export default {
    data() {
      return {
        msg: 'hello',
      };
    },
    methods: {
      getMsg(res) {
        console.log(res);
      },
    },

    components: { test },
  };
</script>
```

## 全局组件通讯

- 监听全局的自定义事件.事件可以由 uni.$emit 触发.回调函数会接收所有传入事件触发函数的额外参数

```语法
uni.$on(eventName,callback)
```

- 实例

```javascript
uni.$on('update', (data) => {
  console.log('监听事件来自update,携带参数msg为' + data);
});
```

## VueX

### 引入 VueX

引入 vuex，在项目根目录创建文件夹 store，并创建文件 index.js（uni-app 已经内置了 vuex，所以我们直接引入就可以了）

### store.js

```js
import Vue from 'vue';
import Vuex from 'vuex';

Vue.use(Vuex);

export default new Vuex.Store({
  state: {
    hasLogin: false, // 登录状态
    userInfo: {}, // 用户信息
  },
  mutations: {
    setHasLogin(state, value) {
      state.hasLogin = value;
      console.log(state.hasLogin);
    },
  },
  actions: {},
  getters: {},
});
```

### main.js 引入

```js
import App from './App';
//引入vuex
import store from './store/store.js';
// #ifndef VUE3
import Vue from 'vue';
Vue.prototype.$store = store;
Vue.config.productionTip = false;
App.mpType = 'app';
const app = new Vue({
  ...App,
  store,
});
app.$mount();
// #endif

// #ifdef VUE3
import { createSSRApp } from 'vue';
export function createApp() {
  const app = createSSRApp(App);
  return {
    app,
  };
}
// #endif
```

### 组件里面使用

```html
<template>
  <view>
    <view class="box">
      <view class="content"> 内容测试 </view>
      <button @click="changeflag">{{hasLogin}}</button>
    </view>
  </view>
</template>

<script>
  import { mapState, mapMutations } from 'vuex';
  export default {
    data() {
      return {};
    },
    computed: {
      ...mapState(['hasLogin']),
    },
    methods: {
      ...mapMutations(['setHasLogin']),
      changeflag() {
        this.setHasLogin(true);
      },
    },
  };
</script>

<style lang="scss">
  .box {
    .content {
      color: red;
      font-size: 48rpx;
    }
  }
</style>
```
