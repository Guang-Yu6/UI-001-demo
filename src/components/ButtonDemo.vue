<template>
  <div>
   shili
  </div>
  <h1>实例</h1>
  <div>
    <ButtonA @click="onClick">父亲组件</ButtonA>
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