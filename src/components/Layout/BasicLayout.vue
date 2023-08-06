<template>
  <div class="basic-layout-container">
    <a-layout style="height: 400px">
      <a-layout-header class="header">
        <GlobalHeader />
      </a-layout-header>
      <a-layout-content class="content">
        <router-view />
      </a-layout-content>
      <a-layout-footer class="footer">
        <a href="https://github.com/Apart123" target="_blank">
          OJ - 在线判题系统 by luying
        </a>
      </a-layout-footer>
    </a-layout>
  </div>
</template>

<script>
import GlobalHeader from "@/components/GlobalHeader.vue";

export default {
  name: "BasicLayout",
  components: { GlobalHeader },
};
</script>

<style scoped lang="less">
.basic-layout-container {
  .header {
    background: red;
    margin-bottom: 20px;
  }
  .content {
    background: linear-gradient(to right, #ddd, #fff);
    margin-bottom: 20px;
  }
  .footer {
    background: #ddd;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    padding: 15px;
    text-align: center;
  }
}
</style>
