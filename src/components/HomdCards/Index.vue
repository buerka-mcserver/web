<script lang="ts" setup>
import { onMounted, ref } from 'vue'

const background = ref<null | HTMLElement>(null)
const video = document.createElement('video')

const videoBackground = () => {
  const videos = [
    '/src/assets/video/0.mp4',
    '/src/assets/video/1.mp4'
  ]
  let i = 0
  video.muted = true
  video.src = videos[i]
  video.addEventListener('canplay', () => {
    video.play()
  })
  const next = () => {
    i == videos.length - 1 ? i = 0 : i++
    video.src = videos[i]
  }

  video.addEventListener('ended', next)
}
videoBackground()

onMounted(() => {
  background.value?.appendChild(video)
})
</script>

<template>
  <div class="background" ref="background"></div>
</template>

<style lang="less" scoped>
.background {
  width: 100%;
  height: 100vh;
  background-color: #aaaa;
  background: url(/src/assets/background/af28f8b1e00781c40a0c13a005d92156.jpg)
    no-repeat center;
  background-size: cover;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  :deep(video) {
    height: 100vh;
    object-fit: contain;
  }
}
</style>