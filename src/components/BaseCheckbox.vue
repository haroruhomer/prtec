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
  .base-checkbox {
    .bc-checkbox{
      -webkit-appearance: none;
      -moz-appearance: none;
      -ms-appearance: none;
      -o-appearance: none;
      appearance: none;
      height: 16px;
      width: 16px;
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
        background: #40e0d0;
      &:checked::before {
        height: 16px;
        width: 16px;
        position: absolute;
        content: '\2713';
        text-align: center;
        line-height: 16px;
      }
      }
    }
  }
</style>
