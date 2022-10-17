<template>
  <button @click="toggle" :class="{checked:x}">
    <span>1</span>
  </button>
</template>

<script lang='ts'>
import {ref} from "vue";

export default {
  setup(){
    const x = ref(false) // 代表切换
    const toggle = () => { // 点击后取反布尔值
      x.value = !x.value
    }
    return {x,toggle}
  }
}
</script>

<style lang='scss' scoped>
$h: 22px;
$h2: $h - 4px;
button {
  //子绝父相
  height: $h;
  width: $h*2;
  border: none;
  background: gray;
  border-radius: $h/2;
  position: relative;
}

span {
  position: absolute;
  top: 2px;
  left: 2px;
  height: $h2;
  width: $h2;
  background: white;
  border-radius: $h2 / 2;
}

button.checked{
  background: blue;
}
button.checked > span {
  left: calc(100% - #{$h2} - 2px);
}
</style>