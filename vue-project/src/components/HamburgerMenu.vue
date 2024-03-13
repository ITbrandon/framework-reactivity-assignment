<script setup>

</script>

<template>
<div class="hamburger-menu">
      <div class="bar"></div>
      <div class="bar"></div>
      <div class="bar"></div>
  </div>
</template>

<style scoped>
.bar {  
  width: 30px;   
  height: 3.5px;   
  background-color: white; 
  margin: 4px 0;   
 } 

 .hamburger-menu { 
   display: none;
   flex-direction: column;   
   cursor: pointer; 
 }


 @media screen and (max-width: 880px) {
  .hamburger-menu {
    display: flex;
  }
 }
</style>