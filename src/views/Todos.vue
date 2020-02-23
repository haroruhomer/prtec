<template>
  <div class="todos">
    <h1>To-do's </h1>
    <div class="todo-list"><h2>Todo</h2><h2>Estado</h2></div>
    <div class="todo-list" v-for="todo in todosUncompleted" :key="todo.id">
      <span>{{todo.title}}</span>
      <BaseCheckbox v-model="todo.completed"/>
    </div>
    <div class="separation"></div>
    <div class="todo-list completed" v-for="todo in todosCompleted" :key="todo.id">
      <span>{{todo.title}}</span>
      <BaseCheckbox v-model="todo.completed"/>
    </div>
  </div>
</template>
<script>
  import BaseCheckbox from "../components/BaseCheckbox";

  export default{
    name: 'Todos',
    components:{
      BaseCheckbox
    },
    data(){
      return{
        todos  : [],
        userId : 0
      }
    },
    mounted(){
      this.userId = this.$route.params.id
      axios.get('https://jsonplaceholder.typicode.com/todos',{
        params:{
          userId : this.userId
        }
      })
      .then((response) => this.todos = response.data )
      .catch((error) => console.log(error))
    },
    computed:{
      todosCompleted(){
        return this.filterByCompleted(true)
      },
      todosUncompleted(){
        return this.filterByCompleted(false)
      }
    },
    methods: {
      filterByCompleted(val){
        return this.todos.filter((todo) => todo.completed == val)
      }
    }
  }
</script>
<style lang="scss">
  $bgCard: #FFFFFF;
  .todos{
    background: $bgCard;
    padding: 25px;
  }
  .todo-list{
    padding: 20px 15px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    &:nth-child(odd){
      background: #F5F6FA;
    }
    &.completed{
      text-decoration: line-through;
    }
  }
  .separation{
    width:80%;
    border: 1px solid rgba(142, 141, 144, 0.98);
    margin: 10px auto;

  }
</style>