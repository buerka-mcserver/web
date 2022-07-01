<script lang="ts" setup>
import { ElButton, ElMessageBox } from 'element-plus'
import 'element-plus/dist/index.css'
import { ElNotification } from 'element-plus'
import { h, ref } from 'vue'
import { CopyOne } from '@icon-park/vue-next'
import { useClipboard } from '@vueuse/core'

const groupNumber = ref('1077364974')

const { copy } = useClipboard()

const openLink = (link: string, timeout = 0) => {
  setTimeout(() => {
    window.open(link)
  }, timeout)
}

const openElNotification = (title: string, text: string, copyText?: string) => {
  ElNotification.success({
    title,
    message: h('div',
      {},
      [
        h('span', {}, text),
        h('div', {
          style: {
            display: 'flex'
          }
        }, [
          h('span', {}, copyText),
          copyText ? h(CopyOne, {
            onClick: copy(copyText),
            style: {
              display: 'flex',
              alignItems: 'center'
            }
          }) : null
        ])
      ]
    ),
    duration: 10000
  })
}

const openQq = () => {
  openElNotification('已唤起qq', '若未唤起，请手动加群', '1077364974')
  openLink('https://jq.qq.com/?_wv=1027&k=QUEvnQFQ', 1000)
}
const openMcBe = () => {
  openElNotification('已唤起mc客户端', '若唤起失败请尝试手动添加', 'mc.buerka.cn')
  openLink('minecraft:?addExternalServer=不二卡服务器|mc.buerka.cn:19132', 1000)
}
const openMcJe = () => {
  copy('play.buerka.cn')
  openElNotification('已复制服务器ip', '请打开游戏手动添加', 'mc.buerka.cn')
}
</script>

<template>
  <div class="join">
    <h1>加入我们</h1>
    <div class="buttons">
      <el-button type="warning" size="large" @click="openQq">加入qq群</el-button>
      <el-button type="success" size="large" @click="openMcJe">添加 java 版服务器</el-button>
      <el-button type="success" size="large" @click="openMcBe">添加基岩版服务器</el-button>
      <el-button type="primary" size="large" @click="openElNotification('开发中', '请耐心等待')">申请白名单</el-button>
    </div>
  </div>
</template>

<style lang="less" scoped>
.join {
  padding: 30px 0;
  .buttons {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
    margin: 25px 0;
    button {
      margin-top: 5px;
    }
  }
}
</style>