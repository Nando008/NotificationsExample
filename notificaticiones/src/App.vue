<script setup>
import { ref } from 'vue';

  let qty = ref(1);

  function addValeu(){
    qty.value++
  }

  function minorValue(){
    if(qty.value > 0){
      qty.value--
    }
  }

/* @ es para directivas de eventos*/
</script>

<template>
  <div class="wrapper">
    <div class="profile">
      <div class="ballon" v-if="qty > 0">{{ qty }}</div>
    </div>

    <div class="button-wrapper">
      
      <div class="button" @click="minorValue">-</div>
      <div class="button" @click="addValeu">+</div>
    </div>

    <div v-if="qty > 0">me escribieron😎 {{ qty }} mensajes</div>
    <div v-else>nadie me escribe😢</div>
  </div>
</template>

<style scoped>

  .button{
    background-color: rgb(36, 133, 179);
    display: inline-block;
    padding: 4px 0;
    border-radius: 4px;
    width: 32px;
    margin: 0 8px;
    color: white;
  }

  .button:hover{
    cursor: pointer;
    background-color: red;
  }
  .button-wrapper{
    
    margin-top: 16px;
    text-align: center;
    margin-bottom: 16px;
  }
  .ballon{
    width: 32px;
    height: 32px;
    background-color: red;
    border-radius: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    color: white;
    position: absolute;
    top: 0;
    right: 0 ;

  }
  .profile{
    background-color: brown;
    width: 160px;
    height: 160px;
    margin: 0 auto;
    border-radius: 100%;
    position: relative;
    background-image: url('https://cdns-images.dzcdn.net/images/artist/fd9922415127264b9708992d5b0908a4/500x500.jpg');
    background-size: cover;
  }
  .wrapper{
    overflow: hidden;
    background-color: rgb(4, 65, 136);
    width: 60%;
    border-radius: 12px;
    margin: 0 auto;
    padding-top: 18px;
    margin-top: 60px;
  }
</style>