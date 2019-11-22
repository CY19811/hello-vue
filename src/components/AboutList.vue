<template>
  <el-tabs type="border-card"id="card">
    <el-tab-pane label="陈宇">
      <p> 陈宇是一个幽默 内向 积极 阳光 爱党 爱国 的 好青年 喜欢打篮球等等各项运动
        对不懂的事情有着极强的求知欲 包括八卦 哈哈哈</p>
    </el-tab-pane>
    <el-tab-pane label="陈虎">
      <div id="app">
        <p v-html="html"></p>
      </div>
    </el-tab-pane>
    <el-tab-pane label=刘仁>
      <p v-if="bol">他是一个内向的人 但是很有趣</p>
      <p v-else="bol">他喜欢看篮球却不怎么打篮球</p>
      <el-button v-on:click="bol=!bol">换一个</el-button>
    </el-tab-pane>
    <el-tab-pane label=付民康>
      <input type="text" v-model="model" placeholder="请输入"></input>
      <p>{{model}}</p>
      <el-button @click="remove">删除</el-button>
    </el-tab-pane>
    <el-tab-pane label=李威>
      <ul>
        <li v-for="(item,index) in list" :key="index">{{item}}</li>
      </ul>
    </el-tab-pane>
  </el-tabs>
</template>

<script>
    export default {
        name: 'AboutList',
        data() {
            return {
                hello: 'Hello V-text',
                html: '<p class = "span-color" style="color: red;">陈虎  我的室友 是一个看见女孩就脸红的自称内向人士  有着一段从高中到现在的让人羡慕的爱情 爱好篮球\n' +
                    '         曾今和我并建作战 在校级篮球比赛中与冠军差一分 大学最大的遗憾之一  现在喜欢rap 只唱不跳</p>',
                bol: true,
                radio: 1,
                model: '',
                list: ['可爱', '活泼', '骚气', '聪明']
            };
        },
        methods: {
            remove() {
                this.model = "";
            }
        }
    };
</script>

<style scoped>
  #card{
    margin-left: 15%;
    margin-right: 15%;
  }
</style>
