<template>
  <div>
    <template v-for="menu in menuList">
      <!--遍历菜单 如果存在children遍历-->
      <el-submenu v-if="menu.children && menu.children.length > 0" :index="menu.path" :key="menu.path">

        <template slot="title">
          <i :class="menu.icon"></i>
          <span slot="title">{{menu.label}}</span>
        </template>


        <MenuItem :menu-list="menu.children"></MenuItem>

      </el-submenu>

      <el-menu-item v-else :index="menu.path" :key="menu.path">
        <i :class="menu.icon"></i>
        <span slot="title">{{menu.label}}</span>
      </el-menu-item>

    </template>
  </div>
</template>

<script>
import MenuItem from '@/components/MenuItem'

export default {
  name: "MenuItem",
  props:['menuList'],
  components:{
    MenuItem
  }
}
</script>

<style scoped>

</style>
