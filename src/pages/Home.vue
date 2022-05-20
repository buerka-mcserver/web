<script lang="ts" setup>
import Nav from '@/components/Nav.vue'
import { Index, Screenshots, FixedImage } from '@/components/HomdCards/'
</script>

<template>
  <Nav></Nav>
  <Index></Index>
  <Screenshots></Screenshots>
  <FixedImage src="/src/assets/screenshots/1.png" :height="200"></FixedImage>
</template>

<style lang="less" scoped>
:deep(h1) {
  text-align: center;
  color: #333;
}
</style>