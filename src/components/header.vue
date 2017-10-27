<template>
  <div class="header">

    <el-input class="search"
              size="small"
              icon="search"
              v-model="input2"
              :on-icon-click="handleIconClick">
    </el-input>
    <ul class="firstnav">
      <li><router-link to="/">首页</router-link></li>
      <li><a href="http://doc.vue-js.com/">vue2.0</a></li>
      <li><a href="https://www.vue-js.com/getstart">参考资料</a></li>
      <li><a href="http://doc.vue-js.com/v2/api/">API</a></li>

      <li><router-link to="/about">关于</router-link></li>
      <li @click="goMessages"><router-link to="/">hello</router-link></li>
      <li><router-link to="/login">登录</router-link></li>
      <li><router-link to="/register">注册</router-link></li>
    </ul>
  </div>

</template>

<script type="text/ecmascript-6">
  export default {
    name: 'header',
    data () {
      return {
        activeIndex: '1',
        input2: ''
      }
    },
    methods: {
      handleIconClick(ev) {
        console.log(ev);
      },
      goMessages () {
        //VueRouter.push({ path: '/messages' })
        //this.$router.push({path: '/messages'});
        console.log("message")
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="css" scoped>
  ul{
    list-style-type: none
  }
  .header{
    /*box-shadow: 0 0 1px rgba(0,0,0,0.25);*/
    box-shadow: 0 1px 4px #ccc;
    font-size: 15px;
    background: #fff;
    position: fixed;
    width: 100%;
    top:0;
    z-index: 10;
  }
  .firstnav{
    display:block;
    /*width: 1000px;*/
    padding:0;
    margin-right: 180px;
    float: right;
  }
  .firstnav>li {
    float: left;
    display: inline-block;
    height: 50px;
    margin: 10px 0;
  }
  .firstnav>li>a{
    line-height: 50px;
    padding:5px 8px;
    margin: 0 5px;
    text-decoration: none;
    color:#333;
    /*border-bottom: 2px solid #41B883;*/
  }
  .firstnav>li>a:hover{
    /*border-bottom: 2px solid #41B883;*/
    background: #F3F3F3;
    border-radius: 2px;
    color: #41B883;
  }
  .logo{
    color: #41B883;
    float: left;
    margin-left:180px;
    margin-top: 10px;
  }
  .logo img{
    display: inline-block;
    width: 50px;
    height: 50px;
    vertical-align: middle;
  }
  .search{
    float: left;
    width:200px;
    margin: 20px;
  }
</style>
