<template>
  <ALayout id="app-viewer" class="container-page">
    <ALayoutHeader class="container-page-header">
      <div class="container-page-header-logo">
        <img :src="LogoImg" alt="logo" />
      </div>
      <div class="container-page-header-menu">
        <AMenu mode="horizontal" theme="light">
          <AMenuItem key="home"><a-icon type="home" />主页</AMenuItem>
          <ASubMenu class="submenu-title-wrapper">
            <template v-slot:title>
              <a-icon type="code-sandbox" />工具合集
            </template>
            <AMenuItem key="dns_log">DNSLog</AMenuItem>
          </ASubMenu>
          <!-- <ASubMenu class="submenu-title-wrapper">
            <template v-slot:title> <a-icon type="history" />History </template>
            <AMenuItem key="dns_query">DNS Query</AMenuItem>
            <AMenuItem key="image2base64">Image To Base64</AMenuItem>
            <AMenuItem key="cidr_calculator">CIDR Calculator</AMenuItem>
          </ASubMenu> -->
        </AMenu>
      </div>
    </ALayoutHeader>
    <ALayoutContent class="container-content">
      <router-view />
    </ALayoutContent>
    <ALayoutFooter class="container-footer">
      Copyright © 2020
      <a href="https://github.com/Buzz2d0/Hyuga">Buzz2d0</a> All Rights
      Reserved.
      <ADivider type="vertical" />
      <img class="icp-footer-logo" :src="icpImg" alt="icp" />
      苏ICP备2020051327号
    </ALayoutFooter>
  </ALayout>
</template>

<script>
export default {
  name: "AppViewer",
  data: () => ({
    LogoImg: require("../assets/logo.png"),
    icpImg: require("../assets/icp.png")
  })
};
</script>

<style lang="scss" scoped>
.container-page {
  width: 100vw;
  max-width: 100vw;
  height: 100vh;
  max-height: 100vh;
  .container-page-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    box-shadow: 0 1px 4px rgba(0, 21, 41, 0.08);
    background-color: #ffffff;
    &-logo {
      img {
        max-width: 100px;
      }
    }
  }
  .container-content {
    height: 100%;
  }
  .container-footer {
    width: inherit;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
  }
  .icp-footer-logo {
    height: 12px;
  }
}
</style>
