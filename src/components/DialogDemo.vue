<template>
  <div>
    外层组件
  </div>
  <h1>示例1</h1>
  <Button @click="toggle">toggle</Button>
  <Dialog v-model:visible="x"></Dialog>
</template>

<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'
import {ref} from 'vue'

export default {
  components: {Dialog, Button},
  setup() {
    const x = ref(false)
    const toggle = () => {
      x.value = !x.value
    }
    return {
      x,
      toggle
    }
  }
}

</script>

<style lang='scss' scoped>

</style>