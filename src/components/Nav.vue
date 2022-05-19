<script lang="ts" setup>

</script>

<template>
  <nav>
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
  background-color: rgba(0, 0, 0, 0.588);
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  padding: 0 15px;
  box-sizing: border-box;
  z-index: 100;
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