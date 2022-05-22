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

    // 切换文案
    index.value == text.length - 1 ? index.value = 0 : index.value++
  }

  video.addEventListener('ended', next)
}
videoBackground()

onMounted(() => {
  background.value?.appendChild(video)
})

const index = ref(0)
const text = [
  {
    title: '1.18原版互通服',
    text: '最新正式版，同时支持 java 版与基岩版'
  },
  {
    title: '丰厚的节日福利',
    text: '除夕、端午、中秋等节日，将发放节日福利'
  },
  {
    title: '时刻保持最新版本',
    text: '第一时间更新版本，保持最新正式版'
  },
  {
    title: '支持离线模式',
    text: '支持离线模式设置皮肤，没有正版也可游玩'
  }
]
</script>

<template>
  <div class="background" ref="background">
    <div class="text">
      <h1>{{ text[index].title }}</h1>
      <div class="hr"></div>
      <p>{{ text[index].text }}</p>
    </div>
    <div class="next"></div>
  </div>
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
  // justify-content: center;
  align-items: center;
  position: relative;
  .next {
    width: 10px;
    height: 10px;
    border: 2px solid #0000;
    border-bottom-color: #fff;
    border-right-color: #fff;
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    margin: 20px auto;
    z-index: 100;
    transform: rotate(-135deg);
    animation: next 2s infinite linear;
  }
  @keyframes next {
    50% {
      transform: translateY(10px) rotate(-135deg);
    }
  }
  :deep(video) {
    width: 100%;
    height: 100%;
    object-fit: cover;
    position: absolute;
  }
  .text {
    z-index: 1;
    max-width: 400px;
    margin-left: 240px;
    margin-right: 10px;
    h1 {
      color: #fff;
      text-align: left;
      margin-bottom: 20px;
      font-size: 35px;
    }
    .hr {
      width: 100%;
      border-top: 1px rgba(255, 255, 255, 0.667) solid;
    }
    p {
      color: #fff;
      font-size: 26px;
      margin: 10px 0;
    }
  }
}

@media screen and (max-width: 1000px) {
  .background {
    .text {
      margin-left: 160px;
    }
  }
}
@media screen and (max-width: 800px) {
  .background {
    .text {
      margin-left: 60px;
    }
  }
}
@media screen and (max-width: 600px) {
  .background {
    .text {
      margin-left: 10px;
    }
  }
}
</style>