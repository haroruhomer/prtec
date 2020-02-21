<template>
  <div class="about">
    <h1>This is an about {{userId}} </h1>
  </div>
</template>
<script>
  export default{
    name: 'Todos',
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
        let filtered = this.todos.filter((todo) => todo.completed == val)
        console.log(filtered);
        return filtered
      }
    }
  }
</script>
