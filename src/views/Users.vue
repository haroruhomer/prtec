<template>
  <div class="users">
    <div class="btn-area">
      <BaseButton msg="+ Add new user"/>
    </div>
    <div class="users-table">
      <h4>Users</h4>
      <table>
        <thead class="thead">
          <tr>
            <th>Id</th>
            <th>Nombre</th>
            <th>Email</th>
            <th>Dirección</th>
            <th>Compañia</th>
            <th>Opciones</th>
          </tr>
        </thead>
        <tbody class="tbody">
          <tr v-for="user in users" :key="user.id">
            <td>{{user.id}}</td>
            <td>{{user.username}}</td>
            <td>{{user.email}}</td>
            <td>{{user.address.street}}</td>
            <td>{{user.company.name}}</td>
            <td><router-link :to="{ name: 'Todos', params: { id: user.id}}">View Todos</router-link></td>
          </tr>
        </tbody>
        <tbody>

        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import BaseButton from '@/components/BaseButton'
export default {
  name: 'Users',
  components:{
    BaseButton
  },
  data(){
    return {
      users : {}
    }
  },
  mounted(){
    axios.get('https://jsonplaceholder.typicode.com/users')
    .then((response)=>{
      this.users = response.data

    })
    .catch((error)=>{
      console.log(error);
    })
  }
}
</script>

<style lang="scss">
  $bgCard : #FFFFFF;
  .btn-area{
    margin-top: 25px;
    margin-bottom: 12px;
  }
  .users-table{
    background: $bgCard;
    padding: 25px;
  }
  table{
    width: 100%;
    text-align: left;
    font-weight: 500;
    .thead{
      color: #9B9EAC;
    }
    .tbody{
      tr:nth-child(odd){
        background: #F5F6FA;
      }
      td{
        padding: 25px 0;
      }
    }
  }
</style>
