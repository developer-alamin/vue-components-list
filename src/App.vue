<script setup>
  import {ref} from 'vue';
  import Header from "./components/header.vue";
  import ButtonCounter from "./components/ButtonCounter.vue";
</script>
<template>
  <div class="container">
    <div class="row">
      <Header/>
    </div> 
    <br>  
    <ButtonCounter :count="10"/><br>
    <ButtonCounter/>
    
  </div>
</template>
<style scoped>

</style>
