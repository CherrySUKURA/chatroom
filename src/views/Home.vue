<template>
  <div class="home">
    <div class="home-content">
      <div class="sidebar">
        <div class="useImg">
          <img src="../assets/logo.png" class="userurl">
        </div>
        <el-menu default-active="1" class="el-menu-vertical-demo" @open="handleOpen" @close="handleClose" :collapse="isCollapse" background-color="#545c64"
        text-color="#fff"
        active-text-color="#fff"
        :router="true">
          <el-menu-item v-for="(item,index) in icon" :key="index" :index="item.index">
            <i :class="item.icon"></i>
            <span slot="title">{{item.title}}</span>
          </el-menu-item>
        </el-menu>
      </div>
      <div class="show-content">
        <router-view to="/About"></router-view>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    // HelloWorld
  },
  data() {
    return {
      isCollapse: true,
      icon: [
        {
          title: "工作",
          icon: "el-icon-menu",
          index: "/work"
        },
        {
          title: "消息",
          icon: "el-icon-chat-line-round",
          index: "/chat"
        },
        {
          title: "文档",
          icon: "el-icon-notebook-1",
          index: ""
        },
        {
          title: "邮件",
          icon: "el-icon-message",
          index: ""
        }
      ]
    }
  },
  methods: {
    handleOpen() {

    },
    handleClose() {

    }
  }
}
</script>

<style scoped>
  .home{
    width: 100%;
    height: 100vh;
    position: relative;
  }
  .home-content{
    width: 900px;
    height: 600px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    border-radius: 30px;
    overflow: hidden;
    display: flex;
    flex-flow: row nowrap;
  }
  .sidebar{
    width: 80px;
    height: 100%;
    background-color:#545c64;
    padding-top: 10px;
  }
  .useImg{
    width: 40px;
    height: 40px;
    border-radius: 50%;
    overflow: hidden;
    background: #ffffff;
    margin:auto;
  }
  .userurl{
    width: 100%;
    height: 100%;
  }
  .el-menu-vertical-demo{
    width: 100%;
    min-height: 400px;
    /* text-align: center; */
    border: none;
    margin-top: 60px;
  }
  .show-content{
    width: 100%;
    height: 100%;
    background: #ffffff;
  }
</style>
