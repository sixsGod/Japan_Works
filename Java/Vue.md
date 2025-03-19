## Vue概要
Vue是一款用于构建用户界面的渐进式的JavaScript框架。（渐进式就是可以不去整站式使用Vue，而只局部使用Vue。因为vue核心包由很多，不必全都用）

- 快速入门
```javascript
<div id="app">
  <h1> {{ msg }} </h1>
</div>

<script type="module">
  import { createApp } from 'https://unpkg.com/vue@3/dist/vue.global.js'

  createApp({
    data() {
      return {
        msg: "hello world"
      }
    }
  }).mount"#app")
```
