<script setup>

</script>

<template>
<button>
  <slot></slot>
  
  </button>
</template>

<style scoped>
button {
  padding: 1rem;
  background-color: orangered;
  color: white;
  font-size: 1.1rem;
  font-weight: bold;
  border: none;
  border-radius: 20px;
  cursor: pointer;
  transition: 0.4s;
  position: absolute;
  top: 99%;
  left: 50%;
  transform: translate(-50%, -50%);
}

button:hover {
  background-color: rgb(164, 45, 2);
}
</style>
