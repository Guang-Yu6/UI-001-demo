<template>
    <div class="topnav">
      <div class="logo" >LOGO</div>
      <ul class="menu">
        <li>菜单1</li>
        <li>菜单2</li>
      </ul>
      <span class="toggleAside" @click="toggleMenu"></span>
    </div>
</template>

<script lang="ts">
import {inject,Ref} from "vue";

export default {
  setup(){
    const asideVisible = inject<Ref<boolean>>('xxx') // get
    console.log('topnav 获取的 visible 为'  + asideVisible.value  )
    //②点击LOGO显示与隐藏切换
    const toggleMenu = () => {
      asideVisible.value = !asideVisible.value
    }
    return {toggleMenu}
  }
}
</script>


<style lang="scss" scoped>
.topnav {
  background: pink;
  display: flex;
  padding: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  z-index: 10;
  justify-content: center;
  align-items: center;
  > .logo {
    max-width: 6em;
    margin-right: auto;
  }
  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;
    > li {
      margin: 0 1em;
    }
  }

  >.toggleAside {
    width: 24px;
    height: 24px;
    background: red;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    display: none;
  }
  // 响应式的
  @media (max-width: 600px) {
    > .menu{display: none;}
    > .logo{margin: 0 auto;}
    > .toggleAside{display: inline-block;}
  }
}
</style>