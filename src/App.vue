<template>
  <el-container :span="24">
    <el-header>
      <el-row type="flex">
        <el-col :span="8">
          <img
            class="logo"
            src="./assets/image/logo.png"
            alt="logo"
            title="LOGO"
          />
        </el-col>
        <el-col :span="8" class="title">
          <h2><b>Readbook</b></h2>
          <p class="little-font text-c">不含购买项目</p>
        </el-col>
        <el-col :span="8">
          <el-button
            class="share btn"
            v-clipboard:copy="message"
            data-toggle="popover"
            title="点击将链接复制到剪切板上"
            icon="el-icon-share"
          >
          </el-button>
        </el-col>
      </el-row>
    </el-header>
    <el-main el-24>
      <el-col
        class="banner"
        :xs="{ span: 18, offset: 3 }"
        :sm="{ span: 8, offset: 3 }"
        :md="{ span: 6, offset: 2 }"
        :lg="{ span: 5, offset: 3 }"
      >
        <el-carousel trigger="click" height="500px">
          <el-carousel-item v-for="item in listImgs" :key="item">
            <img :src="item" alt="app details" srcset="" />
          </el-carousel-item>
        </el-carousel>
      </el-col>
      <el-col
        class="down"
        :xs="{ span: 18, offset: 3 }"
        :sm="{ span: 10, offset: 1 }"
        :md="{ span: 6, offset: 1 }"
        :lg="{ span: 4, offset: 2 }"
      >
        <ul>
          <li>
            <el-button class="btn">
              <a
                class="down-link"
                href="https://read.dusiyi.com/app"
                title="Web APP"
              >
                Web App
              </a>
            </el-button>
          </li>
          <li>
            <el-button class="btn">
              <a
                class="down-link"
                href="https://read.dusiyi.com/download/apk/readapp"
                title="Readbook app down link in Android"
              >
                Android下载
              </a>
            </el-button>
          </li>
          <li>
            <el-button class="btn">
              <a
                class="down-link"
                href="https://testflight.apple.com/join/yq0jJo3b"
                title="Readbook app down link in iOS(TestFlight)"
              >
                Android下载
              </a>
            </el-button>
          </li>
        </ul>
        <p class="little-font">或识别二维码下载</p>
        <img
          class="qr-img"
          src="https://read.dusiyi.com/download/qr"
          alt="Readbook app down QR"
          title="Readbook app down QR"
        />
      </el-col>
      <el-col
        class="details"
        :xs="{ span: 18, offset: 3 }"
        :sm="{ span: 23, offset: 1 }"
        :md="{ span: 7, offset: 1 }"
        :lg="{ span: 5, offset: 1 }"
      >
        <h5 class="text-c">关于此项目</h5>
        <ul class="appinfo">
          <li>版本：1.0.0</li>
          <li>开发者：Evenpool</li>
          <li>无内购项目</li>
          <li>操作简单</li>
          <li>不涉及敏感权限</li>
          <li>
            <ol>
              <li>真实打卡，阅读文章后才会有打卡记录，挑战不自律</li>
              <li>智能录音，语音识别多元化，采用多种算法保障语音识别的准确</li>
              <li>计划管理，最多同时同阶段进行三本书，保证不堆积超额的计划</li>
              <li>反馈方便，有问题可以直接截图app界面，反馈给我们</li>
              <li>更多功能，敬请期待</li>
            </ol>
          </li>
        </ul>
      </el-col>
    </el-main>
    <el-footer>
      <h4>&copy;Evenpool,保留所有权利</h4>
    </el-footer>
  </el-container>
</template>
<script>
export default {
  computed: {
    listImgs: function () {
      const imgs = ["07", "01", "02", "03", "04", "05", "06"];
      const res = [];
      for (let i = 0; i < imgs.length; i++) {
        res.push(`../static/img/${imgs[i]}.jpg`);
      }
      return res;
    },
  },
  data() {
    return {
      message: "https://read.dusiyi.com/download/apk/readapp",
    };
  },
};
</script>
<style>
.logo {
  width: 120px;
  border-radius: 15px;
}
.el-header {
  background: #fbead4;
  padding: 20px 0px 20px;
  height: 170px !important;
  text-align: center;
}
.el-footer {
  background: #fbead4;
  text-align: center;
  height: 100px !important;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #755548;
}
.el-carousel img {
  width: 100%;
}

.el-carousel__item {
  background-color: #fff;
}
.el-carousel__button {
  width: 0px;
  background-color: #99a9bf;
}
.little-font {
  font-size: smaller;
  color: #998a7e;
}
.title h2 {
  text-align: center;
}

.banner,
.details,
.down {
  margin-top: 30px;
  height: 500px;
}
.share {
  background: #fbead4;
  border: #998a7e21 0px solid;
  font-size: 30px;
}
.share:hover {
  color: #755548;
  border: none !important;
  border-radius: 10px;
}
.btn:hover {
  background: #75554833;
  border: #998a7e 1px solid;
}
.btn,
a.down-link {
  text-decoration: none;
  color: #755548;
}
.down,
.down ul {
  text-align: center;
}
.down ul {
  padding: 0;
}
.down ul li {
  list-style: none;
  margin-top: 10px;
}
.qr-img {
  width: 200px;
  margin: 0 auto;
}
.details {
  font-size: 16px;
}
.text-c {
  text-align: center;
}
.text-l {
  text-align: left;
}
</style>
