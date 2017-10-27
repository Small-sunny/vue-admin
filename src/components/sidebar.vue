<template>
  <el-menu mode="vertical" theme="dark" :default-active="$route.path">
    <sidebar-item></sidebar-item>
  </el-menu>
</template>

<script>
  import SidebarItem from './sidebarItem';
  export default {
    components: { SidebarItem },
  }
</script>

<style scoped>
  .el-menu {
    min-height: 100%;
    width:210px;
    background-color: #424F63;
  }
</style>

