<script lang="ts" setup>
import UserPreference from '@/components/Illustrations/UserPreference.vue'
import Conversion from '@/components/Illustrations/Conversion.vue'
import StandardDelivery from '@/components/Illustrations/StandardDelivery.vue'
</script>

<template>
  <div class="advantages">
    <h1>我们的优势</h1>
    <div class="icons">
      <div class="item">
        <div class="icon">
          <UserPreference></UserPreference>
        </div>
        <span>体验好</span>
      </div>
      <div class="item">
        <div class="icon">
          <Conversion style="transform: translateX(8px);"></Conversion>
        </div>
        <span>高性能</span>
      </div>
      <div class="item">
        <div class="icon">
          <StandardDelivery></StandardDelivery>
        </div>
        <span>互通服</span>
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
.advantages {
  width: 100%;
  background-color: #eef0f5;
  .icons {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-between;
    max-width: 800px;
    margin: 10px auto;
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
        svg {
          width: 120px;
          height: 120px;
        }
      }
    }
  }
}
</style>