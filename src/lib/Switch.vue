<template>
  <button @click="toggle" :class="{checked:value}">
    <span>1</span>
  </button>
</template>

<script lang='ts'>

export default {
  props:{
    value:Boolean,
  },
  setup(props,context){
    // const x = ref(false) // 代表切换
    const toggle = () => { // 点击后取反布尔值
      // x.value = !x.value
      context.emit('update:value',!props.value)
    }
    return {toggle}
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
  transition: all 250ms;
}

button.checked{ // 为什么要加checked？
  background: #1890ff;
}
button.checked > span {
  left: calc(100% - #{$h2} - 2px);
}

button:focus { // 按钮边框
  outline: none;
}

button:active{
  > span {width: $h2 + 4px;}
}
button.checked:active{
  > span {width: $h2 + 4px; margin-left: -4px;}
}
</style>