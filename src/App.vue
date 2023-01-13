<template>
  <el-container>
    <el-header>
      <el-row type="flex" justify="space-around">
        <div :span="3">
          <img
            class="logo"
            src="./assets/image/logo.png"
            alt="logo"
            title="LOGO"
          />
        </div>
        <div :span="6" class="title">
          <h2><b>Readbook</b></h2>
          <p class="little-font">不含购买项目</p>
        </div>
        <div :span="3">
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
      </el-row>
    </el-header>
    <el-main></el-main>
    <el-footer></el-footer>
  </el-container>
</template>
<script>
export default {
  data() {
    return {
      message: "",
    };
  },
};
</script>
<style>
.logo {
  width: 150px;
  border-radius: 15px;
}
.el-header {
  background: #fbead4;
  padding: 50px 0px 40px;
  height: 240px !important;
  width: 100%;
}
</style>
