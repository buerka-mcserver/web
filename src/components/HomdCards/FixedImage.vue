<script lang="ts" setup>
const props = defineProps({
  src: String,
  height: Number
})
</script>

<template>
  <div class="fixed-image" :style="{ backgroundImage: `url(${src})`, height: height + 'px' }"></div>
</template>

<style lang="less" scoped>
.fixed-image {
  background-attachment: fixed;
  width: 100%;
  min-height: 100px;
}
</style>