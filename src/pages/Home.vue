<script lang="ts" setup>
import Nav from '@/components/Nav.vue'
import { Index, Screenshots, FixedImage, Advantages, Status, Join, Footer } from '@/components/HomdCards/'
import staticList from '@/assets/staticList'
</script>

<template>
  <Nav></Nav>
  <Index></Index>
  <Screenshots></Screenshots>
  <FixedImage :src="staticList.FixedImage[0]" :height="500"></FixedImage>
  <Advantages></Advantages>
  <FixedImage :src="staticList.FixedImage[1]" :height="500"></FixedImage>
  <Status></Status>
  <FixedImage :src="staticList.FixedImage[2]" :height="500"></FixedImage>
  <Join></Join>
  <Footer></Footer>
</template>

<style lang="less" scoped>
:deep(h1) {
  text-align: center;
  color: #333;
}
</style>