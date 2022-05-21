<script lang="ts" setup>
import Nav from '@/components/Nav.vue'
import { Index, Screenshots, FixedImage, Advantages, Status, Join, Footer } from '@/components/HomdCards/'
</script>

<template>
  <Nav></Nav>
  <Index></Index>
  <Screenshots></Screenshots>
  <FixedImage src="/src/assets/screenshots/3.png" :height="300"></FixedImage>
  <Advantages></Advantages>
  <FixedImage src="/src/assets/screenshots/2.jpg" :height="300"></FixedImage>
  <Status></Status>
  <FixedImage src="/src/assets/screenshots/1.png" :height="300"></FixedImage>
  <Join></Join>
  <Footer></Footer>
</template>

<style lang="less" scoped>
:deep(h1) {
  text-align: center;
  color: #333;
}
</style>