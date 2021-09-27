// 模板
<template>
  <div class="wrapper">
    <!-- 头部 -->
    <v-head></v-head>
    <!-- 侧边栏 -->
    <v-sidebar></v-sidebar>
    <!-- 内容填充 -->
    <div class="content">
        <!-- 初始渲染的过渡 -->
      <transition name="move" mode="out-in">
          <!-- 当前主页路由视图 -->
        <router-view></router-view>
      </transition>
    </div>
  </div>
</template>

<script>
// 导入自定义头部和自定义侧边栏
import vHead from "./Header.vue";
import vSidebar from "./Sidebar.vue";
//导出
export default {
  components: {
    vHead,
    vSidebar,
  },
};
</script>
