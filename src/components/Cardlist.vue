<template>
  <div class="card-list">
    <div slot="header" class="clearfix" v-for="(item,index) in list" :key="index">
      <el-card class="box-card">
        <div slot="header" class="clearfix">
          <span>{{item.title}}</span>
        </div>
        <div class="text item">
          {{item.context}}
        </div>
      </el-card>
    </div>
  </div>
</template>

<script>
    import Ssheader from "./ssheader";

    export default {
        name: 'Cardlist',
        components: {Ssheader},
        data() {
            return {
                url: 'https://api.myjson.com/bins/8w79i',
                list: []
            };
        },
        created() {
            this.fetch();
        },
        methods: {
            async fetch() {
                const {data} = await this.$http.get(this.url);
                this.list = data.Cradlist;
            },
        }
    };
</script>

<style scoped>
  .item {
    margin-bottom: 18px;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }

  .clearfix:after {
    clear: both
  }

  .box-card {
    width: 480px;
    margin: 20px auto;
    text-align: left;
  }
</style>
