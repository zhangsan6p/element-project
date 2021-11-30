<template>
  <el-container style="height: 100%">
    <el-header
        style="
        font-size: 21px;
        background-color: #167bd8;
        color: #fff;
        display: flex;
        justify-content: space-between;
        align-items: center;
      "
    >
      <div>Vue、Element、Spring Boot前后端分离权限管理系统开发实战</div>
      <div class="header-right">
        <img class="userImg" src="../assets/images/avatar.jpg" />
        <div class="header-times">
          <div class="user-info">欢迎你，张明</div>
          <div>{{date}}</div>
        </div>
      </div>
    </el-header>
    <el-container>
      <el-aside width="auto"  style="border-right: 1px solid #e6e6e6;">
        <MenuBar></MenuBar>
      </el-aside>
      <el-container>
        <el-main>Main</el-main>
        <el-footer
            style="
            display: flex;
            justify-content: center;
            align-items: center;
            background-color: cadetblue;
            height: 50px;
            color: #fff;
          "
        >Copyright © 2020 - 2021 . 秘咖学堂.All Rights Reserved</el-footer
        >
      </el-container>
    </el-container>
  </el-container>
</template>

<script>
import MenuBar from "@/components/MenuBar";
var $vueIndex;
export default {
  data() {
    return {
      date: "",
    };
  },
  mounted() {
    $vueIndex = this;
    this.showTime();
    setInterval(function () {
      $vueIndex.showTime();
    }, 1000);
  },
  methods: {
    showTime() {
      var week = new Array(
          "星期日",
          "星期一",
          "星期二",
          "星期三",
          "星期四",
          "星期五",
          "星期六"
      );
      var date = new Date();
      var year = date.getFullYear();
      var month = date.getMonth() + 1;
      var day = date.getDate();
      var hour = date.getHours();
      var minutes = date.getMinutes();
      var second = date.getSeconds();
      this.date =
          year +
          "." +
          (month < 10 ? "0" + month : month) +
          "." +
          day +
          "" +
          " " +
          hour +
          ":" +
          minutes +
          ":" +
          (second < 10 ? "0" + second : second) +
          " " +
          (week[date.getDay()] || "");
    },
  },
  components:{
    MenuBar
  }
};
</script>

<style scoped>
.home {
  height: 100vh;
}

.userImg {
  height: 50px;
  width: 50px;
  border-radius: 50%; /*头像定义为圆形*/
}

.header-right {
  display: flex;
}

.header-times {
  margin: 0px 10px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  font-size: 15px;
}

.user-info {
  font-weight: 600;
}

</style>
