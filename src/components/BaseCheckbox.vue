<template>
  <div class="base-checkbox">
    <input class="bc-checkbox" type="checkbox" :checked="value" @input="emitInput($event)"/>
  </div>
</template>

<script>
  export default {
    name: 'BaseCheckbox',
    props:{
      value:{
        type: Boolean
      }
    },
    data (){
      return {

      }
    },
    methods:{
     emitInput(event){
       this.$emit('input', event.target.checked)
     }
    }
  }
</script>

<style lang="scss">
  $font-size:30px;
  .base-checkbox {
    .bc-checkbox{
      -webkit-appearance: none;
      -moz-appearance: none;
      -ms-appearance: none;
      -o-appearance: none;
      appearance: none;
      height: $font-size;
      width: $font-size;
      background: #cbd1d8;
      border: none;
      border-radius: 5px;
      color: #fff;
      cursor: pointer;
      position: relative;
      &:hover {
        background: #9faab7;
      }
      &:checked {
        background: #3fe04d;
      &:checked::before {
        height: $font-size;
        width: $font-size;
        position: absolute;
        content: '\2713';
        text-align: center;
        line-height: $font-size;
      }
      }
    }
  }
</style>
