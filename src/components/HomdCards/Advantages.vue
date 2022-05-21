<script lang="ts" setup>
import UserPreference from '@/components/Illustrations/UserPreference.vue'
import Conversion from '@/components/Illustrations/Conversion.vue'
import StandardDelivery from '@/components/Illustrations/StandardDelivery.vue'
import AdvantagesIcon from './AdvantagesIcon.vue'
import { ref } from 'vue'

const text = ref('我们拥有高性能的家里云主机，支持ipv4与ipv6，拒绝任何卡顿！给您带来更棒，更畅快的游戏体验。')
const setText = (t: string) => {
  text.value = t
}
</script>

<template>
  <div class="advantages">
    <h1>我们的优势</h1>
    <div class="icons">
      <AdvantagesIcon text="体验好" @hover="setText('游戏体验好')">
        <UserPreference></UserPreference>
      </AdvantagesIcon>
      <AdvantagesIcon
        text="高性能"
        @hover="setText('我们拥有高性能的家里云主机，支持ipv4与ipv6，拒绝任何卡顿！给您带来更棒，更畅快的游戏体验。')"
      >
        <Conversion style="transform: translateX(8px);"></Conversion>
      </AdvantagesIcon>
      <AdvantagesIcon text="互通服" @hover="setText('同时支持je，be进入')">
        <Conversion style="transform: translateX(8px);"></Conversion>
      </AdvantagesIcon>
    </div>
    <div class="text">{{ text }}</div>
  </div>
</template>

<style lang="less" scoped>
.advantages {
  width: 100%;
  background-color: #eef0f5;
  padding: 50px 0;
  .icons {
    max-width: 800px;
    margin: 10px auto;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: space-around;
    cursor: pointer;
  }
  .text {
    max-width: 800px;
    min-height: 3em;
    margin-top: 20px;
    transform: translateX(-50%);
    margin-left: 50%;
    width: 100%;
    font-size: 20px;
  }
}
</style>