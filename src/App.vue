<template>
  <router-view/>
</template>

<script lang="ts">
import {ref, provide} from 'vue'
import {router} from "./router";

export default {
  name: 'App',
  setup() {
    // 通过获取页面的宽度来获取页面是否是true还是false
    const width = document.documentElement.clientWidth
    const asideVisible = ref(width <= 600 ? false : true) // 布尔值
    provide('xxx', asideVisible) // xxx是暗号，子组件要说出暗号才可以接收它的值
    router.afterEach(()=>{
      if (width <= 600) {
        asideVisible.value = false
      }
    })
  }
}
</script>
