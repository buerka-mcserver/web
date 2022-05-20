<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Pagination, Autoplay } from 'swiper'
import 'swiper/css'
import 'swiper/css/pagination'
const modules = [
  Autoplay, Pagination
]
</script>

<template>
  <div class="screenshots">
    <h1>屏幕截图</h1>
    <swiper
      :modules="modules"
      :slides-per-view="3"
      :space-between="10"
      loop
      autoplay
      :pagination="{
        // dynamicBullets: true
      }"
    >
      <swiper-slide>
        <img src="/src/assets/screenshots/1.png" alt="屏幕截图" />
      </swiper-slide>
      <swiper-slide>
        <img src="/src/assets/screenshots/2.jpg" alt="屏幕截图" />
      </swiper-slide>
      <swiper-slide>
        <img src="/src/assets/screenshots/3.png" alt="屏幕截图" />
      </swiper-slide>
    </swiper>
  </div>
</template>

<style lang="less" scoped>
.screenshots {
  padding: 50px 0;
  :deep(.swiper-slide) {
    height: 210px;
    width: 400px;
  }
  :deep(img) {
    object-fit: cover;
    width: 100%;
    height: 100%;
  }
  .swiper {
    margin: 10px 20px;
    user-select: none;
  }
}
</style>