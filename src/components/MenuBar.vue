<template>
  <el-menu default-active="$route.path"
           class="el-menu-vertical-demo"
           @open="handleOpen"
           @close="handleClose"
           :collapse="isCollapse"
           unique-opened="true">

    <MenuItem :menuList="menuList"></MenuItem>

  </el-menu>
</template>

<script>
import MenuItem from "@/components/MenuItem";
import {mapState} from "vuex";
export default {
  name: "MenuBar",
  components:{
    MenuItem
  },
  computed:{
    ...mapState(
        {
          isCollapse:
              state => state.MenuStore.isCollapse,
          menuList:
              state => state.MenuStore.menuList
        }
    )
  },
  data() {
    return {

    };
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  }
}
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  min-height: 400px;
}
</style>
