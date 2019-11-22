<template xmlns="http://www.w3.org/1999/html">
  <div class="home">
    <el-input v-model="from.username" placeholder="    请输入用户名 " style="width:20%"
              id="el-input-text"></el-input>
    <br><br><br>
    <el-input v-model="from.password" placeholder="请输入密码" show-password
              style="width:20%"></el-input>
    <br><br><br>
    <el-button type="primary" icon="el-icon-edit" @click="handleClick" style="width: 10%">登录
    </el-button>
  </div>

</template>

<script>
    import Header from "../components/ssheader";
    import Ssheader from "../components/ssheader";

    export default {
        name: 'home',
        components: {Header, Ssheader},
        data() {
            return {
                from: {
                    username: '',
                    password: ''
                },
                list: []
            };
        },
        created() {
        },
        methods: {
            handleClick() {
                if (this.from.username === '' || this.from.password === '') {
                    this.$message.warning('用户名或密码不能为空！');
                } else if (this.from.username !== '11' || this.from.password !== '11') {
                    this.$message.warning('账号或密码错误！');
                } else {
                    this.$router.push({path: '/about'});
                }
            }
        }
    };

</script>
<style>
  #el-input-text {
    padding: 0;
    margin-top: 50%;
  }
</style>

