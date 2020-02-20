<template>
  <button class="btn btn-primary btn-add--user" type="button" name="button">
    {{msg}}
  </button>
</template>

<script>
export default {
  name: 'BaseButton',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.btn{
  border-radius: 8px;
  padding: 16px;
  color: #FFFFFF;
  border: none;
  &.btn-primary{
    background: #0054FE;
  }
}
</style>
