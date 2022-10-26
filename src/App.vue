<template>
  <div id="app">
    <div class="container-fluid">
      <header class="row justify-content-evently">
        <div class="col-3">
          <img
            src="./assets/image/logo.png"
            alt="logo"
            sizes="width:50px"
            title="LOGO"
          />
        </div>
        <div class="col-6 title">
          <h2><b>Readbook</b></h2>
          <p class="little-font">不含购买项目</p>
        </div>
        <div class="col-3">
          <button
            class="btn no-border"
            v-clipboard:copy="message"
            data-toggle="popover"
            title="点击将链接复制到剪切板上"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="20"
              height="20"
              fill="currentColor"
              class="bi bi-share"
              viewBox="0 0 20 20"
            >
              <path
                d="M13.5 1a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3zM11 2.5a2.5 2.5 0 1 1 .603 1.628l-6.718 3.12a2.499 2.499 0 0 1 0 1.504l6.718 3.12a2.5 2.5 0 1 1-.488.876l-6.718-3.12a2.5 2.5 0 1 1 0-3.256l6.718-3.12A2.5 2.5 0 0 1 11 2.5zm-8.5 4a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3zm11 5.5a1.5 1.5 0 1 0 0 3 1.5 1.5 0 0 0 0-3z"
              />
            </svg>
          </button>
        </div>
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
                <img
                  class="img-fluid"
                  :src="require('./assets/image/' + item + '.png')"
                  alt=""
                />
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
            <div
              id="carouselExampleControls"
              class="carousel slide col-12 col-lg-10 offset-lg-1"
              data-bs-ride="carousel"
            >
              <div class="carousel-inner">
                <div class="carousel-item active">
                  <img
                    src="./assets/image/logo.png"
                    class="d-sm-block w-100"
                    alt="app details"
                  />
                </div>
                <div class="carousel-item">
                  <img
                    src="./assets/image/start.png"
                    class="d-sm-block w-100"
                    alt="app details"
                  />
                </div>
                <div
                  class="carousel-item"
                  v-for="item in this.listImgs"
                  :key="item"
                >
                  <img
                    :src="require('./assets/image/' + item + '.png')"
                    alt=""
                  />
                </div>
              </div>
              <button
                class="carousel-control-prev"
                type="button"
                data-bs-target="#carouselExampleControls"
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
                data-bs-target="#carouselExampleControls"
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
          <div class="down col-8 col-md-4 offset-2 offset-md-0">
            <h5>下载详情</h5>
            <button type="button" class="btn btn-outline-primary">
              <a
                href="https://read.britao.com/download/apk/readapp"
                title="Readbook app down link"
                >点击下载
              </a>
            </button>
            <br />
            <p class="little-font">或识别二维码下载</p>
            <img
              class="img-fluid"
              src="https://read.britao.com/download/qr/readapp"
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
      <footer class="footer">
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
      listImgs: ["01", "02", "03", "04"],
      list: ["logo.png", "start.png"],
      message: "https://read.britao.com/download/apk/readapp",
    };
  },
  methods: {
    onCopy: function () {
      // new bootstrap.Alert(this.mes_suc);
      alert(this.mes_suc);
    },
    onError: function () {
      // new bootstrap.Alert(this.mes_f);
      alert(this.mes_f);
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
.btn {
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
.btn:hover {
  /* background-color: #755548; */
  background-color: #c9b097;
  border: #998a7e 1px solid;
  color: #755548;
}
a {
  text-decoration: none;
  color: #755548;
}
a:hover {
  color: #755548;
}
.banner {
  /* padding-top: 50px; */
  height: 400px;
  /* background: #755548; */
}
.banner .carousel-item {
  /* transform: scale(0.6); */
  /* width: 300px !important; */
  height: 400px;
}
.banner .carousel-item img {
  height: 400px;
  border-radius: 50px;
}
.img-list {
  padding: 0;
}
.img-list li {
  list-style-type: none;
  margin: 0px 5px 10px;
  border: 1px solid #755548;
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
