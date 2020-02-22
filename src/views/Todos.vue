<template>
  <div class="about">
    <h1>This is an about {{userId}} </h1>
    <div class="todo-list" v-for="todo in todosUncompleted" :key="todo.id">
      <span>{{todo.title}}</span>
      <BaseCheckbox v-model="todo.completed"/>
    </div>
    <div class="todo-list" v-for="todo in todosCompleted" :key="todo.id">
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
  .todo-list{
    display: flex;
  }
</style>