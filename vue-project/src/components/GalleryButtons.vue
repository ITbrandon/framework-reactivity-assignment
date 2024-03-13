<script setup>
import {defineEmits} from 'vue';

const props = defineProps({
  data: {
    type: Array,
    required: true
  }
})
</script>

<template>
<ul>
  <li v-for="(banner, i) in props.data" @click="$emit('changePage', i)" :key="i"></li>
</ul>
</template>

<style scoped>
ul {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 0.5rem;
  list-style-type: none;
  position: absolute;
  top: 107%;
  left: 50%;
  transform: translate(-50%, -50%);
}

li {
  background-color: orangered;
  border-radius: 50%;
  height: 10px;
  width: 10px;
  cursor: pointer;
  transition: 0.3s;
}

li:hover {
  background-color: white;
}
</style>