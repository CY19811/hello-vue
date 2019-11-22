<template>
  <div id="app">
    <div id="nav">
      <el-menu class="el-menu-demo" mode="horizontal" id="menu">
        <el-menu-item index="1">
          <router-link to="/">
            <el-image style="width: 68px;height: 60px;padding: 0" :src="url"></el-image>
          </router-link>
        </el-menu-item>
        <el-menu-item index="2">
          <router-link to="/">登录</router-link>
        </el-menu-item>
        <el-menu-item index="3">
          <router-link to="/about">关于</router-link>
        </el-menu-item>
        <el-menu-item index="4">
          <router-link to="/todo">Todo</router-link>
        </el-menu-item>
        <el-menu-item index="4">
          <router-link to="/card">Card</router-link>
        </el-menu-item>
      </el-menu>
    </div>
    <div class="line"></div>
    <div style="overflow:auto"></div>
  </div>
</template>

<script type="text/javascript">
    const scrollBackground = true;
    export default {
        name: "ssheader",
        data() {
            return {
                url: 'https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=92a7cba0edcd7b89fd6132d16e4d29c2/1b4c510fd9f9d72a26f9db77df2a2834349bbb3f.jpg',
                activeIndex: '1',
                activeIndex2: '1'
            };
        },
        methods: {
            handleSelect(key, keyPath) {
                console.log(key, keyPath);
            }
        }
    }
</script>

<style lang="less">
  .login-container {
    position: fixed;
    height: 100%;
    width: 100%;
    background-image: url(https://static.zhihu.com/heifetz/assets/sign_bg.db29b0fb.png);
  }
</style>
