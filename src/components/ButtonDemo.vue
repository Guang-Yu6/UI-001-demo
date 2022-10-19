<template>
  <div>
   shi
  </div>
  <h1>实例</h1>
  <div>
    <ButtonA>你好</ButtonA>
    <ButtonA theme="button">正常按钮</ButtonA>
    <ButtonA theme="link">连接按钮</ButtonA>
    <ButtonA theme="text">文本按钮</ButtonA>
  </div>

</template>

<script lang='ts'>
import ButtonA from '../lib/Button.vue'
export default {
  components:{ButtonA},

  setup(){
    const onClick = () =>{
      console.log('ni')
    }
    return {onClick}
  }
}
</script>

<style lang='scss' scoped>

</style>