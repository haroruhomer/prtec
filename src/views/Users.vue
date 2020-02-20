<template>
  <div class="users">
    <div class="btn-area">
      <BaseButton msg="+ Add new user"/>
    </div>
    <div class="users-table">
      <h4>Users</h4>
      <table>
        <thead>
          <tr>
            <th>Id</th>
            <th>Nombre</th>
            <th>Apellido</th>
            <th>Email</th>
            <th>Dirección</th>
            <th>Compañia</th>
            <th>Opciones</th>
          </tr>
        </thead>
        <tbody>
          <tr>

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
    this.users={}
  }
}
</script>
<style lang="scss">
  .btn-area{
    margin-top: 25px;
    margin-bottom: 12px;
  }
</style>
