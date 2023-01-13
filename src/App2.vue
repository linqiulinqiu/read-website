<template>
  <div id="app">
    <div class="container-fluid">
      <header class="row justify-content-evently">
       
      </header>
      <div class="content trunk">
        <div class="row justify-content-evently">
          <div class="d-block d-sm-none col-12 img-list">
            <ul class="col-12">
              <li
                class="col-5"
                v-for="(item, index) in listImgs"
                :key="index"
                style="float: left"
              >
                {{ item }}
                <img class="" alt="App details" :src="item" />
              </li>
            </ul>
          </div>
          <div
            class="
              d-none d-sm-block
              banner
              col-sm-8
              offset-sm-2
              col-md-4
              offset-md-0
            "
          >
            <div class="col-12 col-lg-10 offset-lg-1">
              <div id="carouselExample" class="carousel slide">
                <div
                  class="carousel-inner"
                  v-for="item in this.listImgs"
                  :key="item"
                >
                  <div class="carousel-item active">
                    <img
                      :src="item"
                      class="d-block w-100"
                      :alt="'app details' + item"
                    />
                  </div>
                </div>
                <button
                  class="carousel-control-prev"
                  type="button"
                  data-bs-target="#carouselExample"
                  data-bs-slide="prev"
                >
                  <span
                    class="carousel-control-prev-icon"
                    aria-hidden="true"
                  ></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button
                  class="carousel-control-next"
                  type="button"
                  data-bs-target="#carouselExample"
                  data-bs-slide="next"
                >
                  <span
                    class="carousel-control-next-icon"
                    aria-hidden="true"
                  ></span>
                  <span class="visually-hidden">Next</span>
                </button>
              </div>
            </div>
          </div>
          <div class="down col-8 col-md-4 offset-2 offset-md-0">
            <h5>下载详情</h5>
            <button type="button" class="btn">
              <a
                class="down-link"
                href="https://read.dusiyi.com/app"
                title="Web APP"
              >
                Web App
              </a>
            </button>
            <button type="button" class="btn">
              <a
                class="down-link"
                href="https://read.dusiyi.com/download/apk/readapp"
                title="Readbook app down link in Android"
              >
                Android下载
              </a>
            </button>
            <button type="button" class="btn">
              <a
                class="down-link"
                href="https://testflight.apple.com/join/yq0jJo3b"
                title="Readbook app down link in iOS(TestFlight)"
              >
                Android下载
              </a>
            </button>
            <br />
            <p class="little-font">或识别二维码下载</p>
            <img
              class="img-fluid"
              src="https://read.dusiyi.com/download/qr"
              alt="Readbook app down QR"
              title="Readbook app down QR"
            />
          </div>
          <div
            class="
              details
              text-l
              col-sm-8
              offset-sm-2
              col-md-4 col-10
              offset-1 offset-md-0
            "
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
                  <li>
                    智能录音，语音识别多元化，采用多种算法保障语音识别的准确
                  </li>
                  <li>
                    计划管理，最多同时同阶段进行三本书，保证不堆积超额的计划
                  </li>
                  <li>反馈方便，有问题可以直接截图app界面，反馈给我们</li>
                  <li>更多功能，敬请期待</li>
                </ol>
              </li>
            </ul>
          </div>
        </div>
      </div>
      <footer class="row footer justify-content-evently">
        <h6>&copy;Evenpool,保留所有权利</h6>
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      list: ["logo.png", "start.png"],
      message: "https://read.dusiyi.com/download/apk/readapp",
    };
  },
  computed: {
    listImgs: function () {
      const imgs = ["07", "01", "02", "03", "04", "05", "06"];
      const res = [];
      for (var i in imgs) {
        res.push(`./assets/${imgs[i]}.jpg`);
      }
      return res;
    },
  },
  methods: {
    onCopy: function () {
      new bootstrap.Alert(this.mes_suc);
      // alert(this.mes_suc);
    },
    onError: function () {
      new bootstrap.Alert(this.mes_f);
      // alert(this.mes_f);
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #755548;
  /* margin-top: 60px; */
}

.little-font {
  font-size: smaller;
  color: #998a7e;
}
.trunk {
  padding: 60px 0px;
}

header,
footer {
  background: #fbead4;
  padding: 50px 0px 40px;
}
header img {
  width: 100px;
  border-radius: 25px;
}
header .title h2 {
  text-align: center;
}
.btn,
.btn-outline-secondary {
  color: #755548;
  border: #755548 1px solid;
}
.no-border {
  border: none;
}
.banner,
.details,
.down {
  margin-top: 30px;
}
.btn:hover,
.btn-outline-secondary:hover {
  background-color: #c9b097;
  border: #998a7e 1px solid;
  color: #755548;
}

a.down-link {
  text-decoration: none;
  color: #755548;
}
a.down-link:hover {
  color: #755548;
}
/* a.down-link:active {
  color: #755548;
  background-color: #c9b097;
} */
.banner {
  height: 400px;
  background: #75554838;
}
.banner .carousel-item {
  height: 400px;
}
.ban-img {
  transform: scale(0.5);
  border-radius: 50px;
  background-color: #998a7e;
}
/* .banner .carousel-item img {
  height: 400px;
} */
.img-list {
  padding: 0;
}
.img-list li {
  list-style-type: none;
  margin: 0px 5px 10px;
  border: 1px solid #755548;
}
.img-list li img {
  widows: 120px;
  height: 500px;
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
.carousel-control-next {
  color: #755548;
}
</style>
