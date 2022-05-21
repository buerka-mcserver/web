<script lang="ts" setup>
import { onMounted, ref } from 'vue'
const color = ref('black')
const setColor = () => {
  if (window.scrollY <= 100) {
    color.value = 'black'
  } else {
    color.value = 'white'
  }
}

onMounted(() => {
  window.addEventListener('scroll', setColor)
})
</script>

<template>
  <nav :class="color">
    <div class="logo">
      <img src="@/assets/buerka@500px.jpg" alt="logo" />
      <span>不二卡服务器</span>
    </div>
  </nav>
</template>

<style lang="less" scoped>
nav {
  width: 100%;
  height: 50px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  padding: 0 15px;
  box-sizing: border-box;
  z-index: 100;
  transition: all 0.5s;
  &.white {
    background-color: #fff;
    box-shadow: 0 1px 5px 0 #3333;
    .logo span {
      color: #333;
    }
  }
  &.black {
    background-color: rgba(0, 0, 0, 0.588);
  }
  .logo {
    display: flex;
    align-items: center;
    img {
      height: 35px;
      border-radius: 50%;
    }
    span {
      font-size: 22px;
      margin-left: 10px;
      color: #fff;
    }
  }
}
</style>