<template>
  <div>
    父亲
    <Switch v-model:value='bool'/>
  </div>
</template>

<script lang='ts'>
import Switch from '../lib/Switch.vue'
import {ref} from "vue";

export default {
  components: {Switch},
  setup() {
    const bool = ref(true)
    return {bool}
  }
}
</script>