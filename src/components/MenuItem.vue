<template>
  <fragment>
    <template v-for="menu in menuList">
      <!--遍历菜单 如果存在children遍历-->
      <el-submenu
          v-if="menu.children && menu.children.length > 0"
          :index="menu.path"
          :key="menu.path">

        <template slot="title">
          <i :class="menu.icon"></i>
          <span style="font-size: 15px;font-weight: 600;" slot="title">{{ menu.label }}</span>
        </template>

        <MenuItem :menu-list="menu.children"></MenuItem>

      </el-submenu>

      <el-menu-item @click="clickMenuA(menu)" v-else :index="menu.path" :key="menu.path">
        <i class="menu.icon"></i>
        <span slot="title">{{ menu.label}}</span>
      </el-menu-item>

    </template>
  </fragment>
</template>

<script>
import MenuItem from '@/components/MenuItem'

export default {
  name: "MenuItem",
  props: ['menuList'],
  components: {
    MenuItem
  },
  methods: {
    clickMenuA(itme){
      this.$store.commit('clickMenuS',itme)
    }
  }
}
</script>

<style scoped>

</style>
