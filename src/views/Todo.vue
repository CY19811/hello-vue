<template>
  <div class="todo-list">
    <Ssheader></Ssheader>
    <br><br>
    <TodoLists :data-source="list">TodoLists</TodoLists>
  </div>
</template>

<script>
    // 导入组件
    // eslint-disable-next-line import/no-self-import,no-unused-var
    import TodoLists from"../components/TodoList";
    import Ssheader from "../components/ssheader";

    export default {
        name: 'Todo',
        components: {
            TodoLists, Ssheader
        },
        data() {
            return {
                url: 'https://api.myjson.com/bins/wy6f2',
                list: []
            };
        },
        created() {
            this.fetch();
        },
        methods: {
            async fetch() {
                const {data} = await this.$http.get(this.url);
                this.list = data.list;
            }
        }
    }
</script>

<style scoped>

</style>
