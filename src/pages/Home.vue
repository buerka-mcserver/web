<script lang="ts" setup>
import Nav from '@/components/Nav.vue'
import { Index, Screenshots, FixedImage, Advantages } from '@/components/HomdCards/'
</script>

<template>
  <Nav></Nav>
  <Index></Index>
  <Screenshots></Screenshots>
  <FixedImage src="/src/assets/screenshots/1.png" :height="300"></FixedImage>
  <Advantages></Advantages>
</template>

<style lang="less" scoped>
:deep(h1) {
  text-align: center;
  color: #333;
}
</style>