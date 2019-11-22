<template>
  <div class="todo-list">
    <input type="text" v-model="todo" placeholder="请输入姓名" id="input-text"></input>
    <el-button type="primary" icon="el-icon-edit" @click="doAdd" id="el-button" circle></el-button>
    <br><br>
    <hr>
    <h1>小组一</h1>
    <ul id="ul1">
      <li v-for="(item,index) in dataSource" :key="index" v-if="!item.done">
        <el-checkbox v-model="item.done" class="el-checkbox">
          <p id="one">{{item.data}}</p>
        </el-checkbox>
        <br>
        <!--          <el-checkbox v-model="item.done">{{item.data}}</el-checkbox>-->
      </li>
      <li v-for="(item,index) in listinput" :key="index" v-if="!item.done">
        <el-checkbox v-model="item.done" class="el-checkbox">
          <p id="one">{{item.text}}
            <el-button @click="remove(key)">删除</el-button>
          </p>
        </el-checkbox>
        <br>
      </li>
    </ul>
    <br>
    <hr>
    <br>
    <h1>小组二</h1>
    <ul id="ul2">
      <li v-for="(item,index) in dataSource" :key="index" v-if="item.done">
        <el-checkbox v-model="item.done" class="el-checkbox">
          <p id="one">{{item.data}}</p>
        </el-checkbox>
        <br>
        <!--          <input type="checkbox" v-model="item.done"><del>{{item.data}}</del>-->
      </li>
      <li v-for="(item,index) in listinput" :key="index" v-if="item.done">
        <el-checkbox v-model="item.done" class="el-checkbox">
          <p id="one">{{item.text}}
            <el-button @click="remove(key)">删除</el-button>
          </p>
        </el-checkbox>
        <br>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: 'TodoList',
        props: {
            dataSource: Array,
        },
        data() {
            return {
                todo: '',
                listinput: []
            };
        },
        methods: {
            doAdd() {
                this.listinput.push({
                    text: this.todo,
                    done: false
                });
                this.todo = '';
            },
            remove(key) {
                this.listinput.splice(key, 1);
            }
        }
    };
</script>
<!--作用域scoped-->
<style scoped lang="less">
  #input-text {
    padding: 20px;
    margin-left: 0%;
  }

  #ul1 {
    margin-left: 20%;
  }

  #ul2 {
    margin-left: 20%;
  }

  #one {
    font-size: x-large;
    color: #000000;
  }

  .el-checkbox {
    color: #000000;
  }

  #el-button {
    margin-left: 3%;
    line-height: 2;
    font-weight: 100;
  }
</style>
