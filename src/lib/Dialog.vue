<template>
<template v-if="visible">
  <div class="gulu-dialog-overlay"></div>
  <div class="gulu-dialog-wrapper">
    <div class="gulu-dialog">
      <header>标题1<span class="gulu-dialog-close"></span></header>

      <main>
        <p>第一行</p>
        <p>第二行</p>
      </main>

      <footer>
        <Button>OK</Button>
        <Button>关闭</Button>
      </footer>
    </div>
  </div>
</template>
</template>

<script lang="ts">
import Button from './Button.vue'

export default {
  props:{
    visible: {
      type: Boolean,
      default: false
    }
  },
  components: {Button}
}
</script>

<style lang="scss">
$radius: 4px;
$border-color: #d9d9d9;
.gulu-dialog {
  background: white;
  border-radius: $radius;
  box-shadow: 0 0 3px fade_out(black, 0.5);
  min-width: 15em;
  max-width: 90%;

  &-overlay { // 灰色背景遮罩层
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: fade_out(black, 0.5);
    z-index: 10;
  }

  &-wrapper {  // 主体
    position: fixed;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    z-index: 11;
  }

  > header {
    padding: 12px 16px;
    border-bottom: 1px solid $border-color;
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 20px;
  }

  > main {
    padding: 12px 16px;
  }

  > footer {
    border-top: 1px solid $border-color;
    padding: 12px 16px;
    text-align: right;
  }

  &-close {
    position: relative;
    display: inline-block;
    width: 16px;
    height: 16px;
    cursor: pointer;

    &::before,
    &::after {
      content: '';
      position: absolute;
      height: 1px;
      background: black;
      width: 100%;
      top: 50%;
      left: 50%;
    }

    &::before {
      transform: translate(-50%, -50%) rotate(-45deg);
    }

    &::after {
      transform: translate(-50%, -50%) rotate(45deg);
    }
  }
}
</style>