<template>
  <div class="sidebar">
      <!-- 菜单 -->
    <el-menu
      :default-active="onRoutes"
      class="el-menu-vertical-demo"
      theme="dark"
      unique-opened
      router
    >
    <!-- 查找项目 -->
      <template v-for="item in items">
          <!-- 若是subs包含子项目，继续v-for循环列出来 -->
        <template v-if="item.subs">
          <el-submenu :index="item.index" :key="item.index">
            <template slot="title">
                <i :class="item.icon"></i>{{ item.title }}
            </template>
            <el-menu-item
              v-for="(subItem, i) in item.subs"
              :key="i"
              :index="subItem.index">
              {{ subItem.title }}
            </el-menu-item>
          </el-submenu>
        </template>
        <!-- 若不是直接显示 -->
        <template v-else>
          <el-menu-item :index="item.index" :key="item.index">
            <i :class="item.icon"></i>{{ item.title }}
          </el-menu-item>
        </template>
      </template>
    </el-menu>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: "el-icon-setting",
          index: "readme",
          title: "简介",
        },
        {
          icon: "el-icon-setting",
          index: "userCenter",
          title: "设置",
          subs: [
            {
              index: "upload",
              title: "文件上传",
            },
            {
              index: "modifyUser",
              title: "修改用户",
            },
            {
              index: "modifyPassword",
              title: "修改密码",
            },
          ],
        },
      ],
    };
  },
  computed: {
    //   绑定路由表
    onRoutes() {
      return this.$route.path.replace("/", "");
    },
  },
};
</script>

<style scoped>
.sidebar {
  display: block;
  position: absolute;
  width: 250px;
  left: 0;
  top: 70px;
  bottom: 0;
  background: #2e363f;
}
.sidebar > ul {
  height: 100%;
}
</style>
