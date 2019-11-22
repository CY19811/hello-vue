<template>
  <div class="about">
    <Ssheader></Ssheader>
    <br><br>
    <el-select v-model="value" placeholder="请选择" clearable>
      <el-option
        v-for="item in options"
        :key="item.value"
        :label="item.label"
        :value="item.value">
      </el-option>
    </el-select>
    <br>
    <br>
    <br>
    <AboutList></AboutList>
  </div>
</template>

<script>
    import Ssheader from "../components/ssheader";
    import TodoList from "../components/TodoList";

    import AboutList from "../components/AboutList";

    export default {
        name: 'about',
        components: {AboutList, TodoList, Ssheader},
        data() {
            return {
                options: [{
                    value: '选项1',
                    label: '陈宇'
                }, {
                    value: '选项2',
                    label: '陈虎'
                }, {
                    value: '选项3',
                    label: '刘仁'
                }, {
                    value: '选项4',
                    label: '付民康'
                }, {
                    value: '选项5',
                    label: '李威'
                }, {
                    value: '选项6',
                    label: '喻齐'
                }],
                value: ''
            };
        }
    };
</script>

<style>
  .bounce-enter-active {
    animation: bounce-in .5s;
  }

  .bounce-leave-active {
    animation: bounce-in .5s reverse;
  }

  @keyframes bounce-in {
    0% {
      transform: scale(0);
    }
    50% {
      transform: scale(1.5);
    }
    100% {
      transform: scale(1);
    }
  }
</style>
