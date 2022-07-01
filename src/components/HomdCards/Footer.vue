<script lang="ts" setup>

</script>

<template>
  <div class="footer">
    <div class="sponsor">
      <div class="qr-code">
        <div>
          <span class="alipay" style="background-image: url('/src/assets/qrCode/alipay.jpg');"></span>
          支付宝
        </div>
        <div>
          <span
            class="wechatpay"
            style="background-image: url('/src/assets/qrCode/wechatpay.jpg');"
          ></span>
          微信
        </div>
        <!-- <div>
          <span class="afadian" style="background-image: url('/src/assets/qrCode/afadian.png');"></span>
          爱发电
        </div>-->
      </div>
    </div>
    <div class="links">
      <div class="friend-link">
        <h3>友链</h3>
        <a href="https://litf.com.cn">Litf blog</a>
        <a href="https://www.alongw.cn">阿龙博客</a>
      </div>
      <div class="about">
        <h3>关于</h3>
        <a href="https://github.com/buerka-mcserver">Github</a>
        <a href="https://jq.qq.com/?_wv=1027&k=QUEvnQFQ">qq群</a>
      </div>
    </div>
    <div class="icp">
      <hr />
      <div>©2020-2022 buerka.cn all rights reserved.</div>
      <div>
        <a href="https://beian.miit.gov.cn/" target="_blank">皖ICP备2022005044号-2</a>
        <!-- <a href="https://beian.miit.gov.cn/">皖公网安备...号</a> -->
      </div>
    </div>
  </div>
</template>

<style lang="less" scoped>
.footer {
  padding: 20px 0;

  display: grid;
  grid-template-columns: 350px 300px;
  grid-template-rows: 1fr 50px;
  grid-column-gap: 0px;
  grid-row-gap: 0px;
  align-items: center;
  justify-items: stretch;
  justify-content: center;

  a {
    text-decoration: none;
    color: #666;
  }
  .links {
    grid-area: 1 / 2 / 2 / 3;
    display: flex;
    justify-content: space-around;
  }
  .sponsor {
    grid-area: 1 / 1 / 2 / 2;
    .qr-code {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      div {
        display: flex;
        flex-direction: column;
        align-items: center;
        span {
          display: inline-block;
          width: 100px;
          height: 100px;
          margin-right: 5px;
          &.alipay {
            background-size: 152px;
            background-position: -23px -75px;
          }
          &.wechatpay {
            background-size: 183px;
            background-position: -40px -44px;
          }
          &.afadian {
            background-size: 679px;
            background-position: -292px -533px;
            // 二维码太小 放大模糊，加对比度
            filter: contrast(133%);
          }
        }
      }
    }
  }
  .friend-link,
  .about {
    display: flex;
    flex-direction: column;
    a {
      color: rgb(19, 19, 19);
      font-size: 14px;
      margin-top: 7px;
    }
  }
  .icp {
    grid-area: 2 / 1 / 3 / 3;
    font-size: 12px;
    margin-top: 20px;
    display: flex;
    flex-direction: column;
    text-align: center;
    justify-content: space-around;
    hr {
      margin: 5px 0;
      border-color: rgba(241, 241, 241, 0.432);
    }
    a {
      margin: 0 3px;
    }
  }
}

@media screen and (max-width: 670px) {
  .footer {
    grid-template-columns: 1fr;
    grid-template-rows: 80px 1fr 50px;
    max-width: 450px;
    margin: auto;
    .links {
      grid-area: 1 / 1 / 2 / 2;
      margin-bottom: 30px;
    }
    .sponsor {
      grid-area: 2 / 1 / 3 / 2;
    }
    .icp {
      grid-area: 3 / 1 / 4 / 2;
    }
  }
}
</style>