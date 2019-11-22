<template>
  <div id="app" style="overflow:auto" CLASS="login-container">
    <router-view/>
  </div>
</template>

<script>
    import Ssheader from "./components/ssheader"

    export default {
        components: {Ssheader},
        data() {
            return {
                url: 'https://gss2.bdstatic.com/-fo3dSag_xI4khGkpoWK1HF6hhy/baike/c0%3Dbaike80%2C5%2C5%2C80%2C26/sign=92a7cba0edcd7b89fd6132d16e4d29c2/1b4c510fd9f9d72a26f9db77df2a2834349bbb3f.jpg'
            };
        }
    };

</script>

<style lang="less">
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }

  #menu {
    margin-left: 25%;
    width: 50%;
  }

  .login-container {
    position: fixed;
    height: 100%;
    width: 100%;
    background-image: url(https://static.zhihu.com/heifetz/assets/sign_bg.db29b0fb.png);
  }
</style>
