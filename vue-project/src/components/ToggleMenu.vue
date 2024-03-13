<script setup>
const props = defineProps({
  isVisible: {
    type: Boolean,
    required: true
  },

  links: {
    type: Array,
    required: true
  }
})

</script>

<template>
    <div v-show="props.isVisible" class="toggle-menu">
      <ul class="toggle-items">
      <li v-for="({title,href},i) in links" :key="i"><a :href="href">{{ title }}</a></li>
      </ul>
    </div>
</template>

<style scoped>
 .toggle-menu {
  position: sticky;
  top: 29.7%;
  height: 340px;
  transition: 0.4s;
  width: 100%;
  background-color: rgba(0, 0, 0, 0.619);
  z-index: 1;
  animation: slideIn 0.3s ease forwards;
 }

 .toggle-items {
  height: 100%;
  list-style-type: none;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly
 }

 li {
  display: block;
  width: 100%;
  height: 100%;
  text-align: center;
  padding: 10px;
  transition: 0.4s;
  cursor: pointer;
 }

 li:hover {
  background-color: white;
 }

 li:hover a {
  color: black
 }

 li a {
  text-decoration: none;
  color: white;
  font-size: 2rem;
  font-weight: bold;
 }

 @media screen and (min-width: 880px) {
  .toggle-menu {
    display: none;
  }
 }

 @keyframes slideIn {
  from {
    opacity: 0;
    transform: translateY(-10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>