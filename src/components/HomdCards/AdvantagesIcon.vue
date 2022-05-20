<script lang="ts" setup>
const props = defineProps({
  text: String,
  desc: String
})
const emits = defineEmits(['hover'])
</script>

<template>
  <div class="item" @mouseover="emits('hover',)">
    <div class="icon">
      <slot></slot>
    </div>
    <span>{{ text }}</span>
  </div>
</template>

<style lang="less" scoped>
.item {
  display: flex;
  flex-direction: column;
  align-items: center;
  transition: all 0.3s;
  border-radius: 10px;
  &:hover {
    background-color: #fff;
  }
  .icon {
    display: flex;
    font-size: 20px;
    transition: all 0.3s;
    &:hover {
      transform: translateY(5px);
    }
    :deep(svg) {
      width: 120px;
      height: 120px;
    }
  }
}
</style>