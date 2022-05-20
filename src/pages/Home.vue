<script lang="ts" setup>
import Nav from '@/components/Nav.vue'
import { Index, Screenshots } from '@/components/HomdCards/'
</script>

<template>
  <Nav></Nav>
  <Index></Index>
  <Screenshots></Screenshots>
</template>

<style lang="less" scoped>
:deep(h1) {
  text-align: center;
  color: #333;
}
</style>