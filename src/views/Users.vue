<template>
  <div class="users">
    <div class="btn-area">
      <button class="btn btn-primary btn-add--user" type="button" name="button">
        + Add new user
      </button>
    </div>
    <div class="users-table">

    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Users',
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
  .btn{
    border-radius: 8px;
    padding: 16px;
    color: #FFFFFF;
    &.btn-primary{
      background: #0054FE;
    }
  }
  .btn-area{
    margin-top: 25px;
    margin-bot: 12px;
  }
</style>
