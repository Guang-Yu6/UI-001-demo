<template>
  <router-view/>
</template>

<script lang="ts">
import {ref,provide} from 'vue'
export default {
  name: 'App',
  setup(){
    const asideVisible = ref(1 > 0) // 1大于0 是true
    provide('xxx',asideVisible)
  }
}
</script>
