<template>
  <button class="gulu-switch" @click="toggle" :class="{'gulu-checked':value}">
    <span>子</span>
  </button>
</template>

<script lang='ts'>

export default {
  props:{  // 接收的是外部的默认状态
    value:Boolean,
  },
  setup(props,context){
    // const x = ref(false) // 代表切换
    const toggle = () => { // 点击后取反布尔值
      // x.value = !x.value
      context.emit('update:value',!props.value)
      // 再传出去外面点击后的状态
    }
    return {toggle}
  }
}
</script>

<style lang='scss'>
$h: 22px;
$h2: $h - 4px;
 .gulu-switch {
    height: $h; width: $h * 2; border: none; background: #bfbfbf; border-radius: $h/2; position: relative;
    > span {
      position: absolute; top: 2px; left: 2px; height: $h2; width: $h2; background: white; border-radius: $h2 / 2; transition: all 250ms;
    }

      &.gulu-checked { background: #1890ff;
        > span { left: calc(100% - #{$h2} - 2px); }
      }
      &:focus { outline: none; }
      &:active {
        > span { width: $h2 + 4px; }
      }

        &.gulu-checked:active {
          > span { width: $h2 + 4px; margin-left: -4px; }
        }
      }
</style>