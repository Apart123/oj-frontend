<template>
  <div class="global-header-container">
    <a-menu
      mode="horizontal"
      :selected-keys="selectKeys"
      @menu-item-click="handleMenuClick"
    >
      <a-menu-item key="0" :style="{ padding: 0 }" disabled>
        <div class="title-bar">
          <img src="@/assets/oj-logo.png" alt="" class="logo" />
          <div class="title">LY-OJ</div>
        </div>
      </a-menu-item>
      <a-menu-item v-for="item in routes" :key="item.path">
        {{ item.name }}
      </a-menu-item>
    </a-menu>
  </div>
</template>

<script setup lang="ts">
import { routes } from "@/router/routes";
import { useRoute, useRouter } from "vue-router";
import { ref } from "vue";

const router = useRouter();

// 默认主页
const selectKeys = ref(["/"]);

// 路由跳转时，更新选中的菜单项
router.afterEach((to, from, failure) => {
  selectKeys.value = [to.path];
});

const handleMenuClick = (key: string) => {
  router.push({
    path: key,
  });
};
</script>

<style scoped lang="less">
.global-header-container {
  box-sizing: border-box;
  width: 100%;
  padding: 20px;
  background-color: var(--color-neutral-2);

  .title-bar {
    display: flex;
    height: 46px;
    align-items: center;

    img {
      width: 46px;
      height: 46px;
    }

    .title {
      font-size: 16px;
      color: var(--color-neutral-8);
      margin: 0 20px;
    }
  }
}
</style>
