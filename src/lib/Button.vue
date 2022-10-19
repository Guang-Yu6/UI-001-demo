<template>
  <div>
    <button v-bind="$attrs">
      <slot/>
    </button>
  </div>
</template>

<script lang='ts'>
export default {
  inheritAttrs:false,
  setup() {

  }
}


</script>


<style lang="scss" scoped>
div {
  background: gray;
}
</style>
