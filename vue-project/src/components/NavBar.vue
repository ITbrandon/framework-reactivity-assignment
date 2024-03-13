<script setup>
import {ref} from 'vue';
import HamburgerMenu from './HamburgerMenu.vue';
import ToggleMenu from './ToggleMenu.vue';

const props = defineProps({
  links: {
    type: Array,
    required: true
  }
})

let isVisible = ref(false);
</script>


<template>
<nav>
  <div class="logo">
    <img src="../assets/miniclip-logo.png" alt="MiniClip Logo" width="100" height="100">
    <article class="logo-text">
      <h1 class="big">MINICLIP</h1>
      <p>PLAY GAMES</p>
    </article>
  </div>
  
  <ul>
    <li v-for="({title, href}, i) in props.links"><a :href="href" target="_blank">{{ title }}</a></li>
  </ul>

  <div @click="isVisible = !isVisible">
  <HamburgerMenu />
  </div>
</nav>
  <ToggleMenu :isVisible="isVisible" :links="links" />
</template>

<style scoped>
nav {
 display: flex;
 justify-content: space-between;
 align-items: center;
 background-color: rgba(0, 0, 0, 0.619);
 padding: 2.5rem;
 width: 100%;
 position: sticky;
 top: 0;
}

h1 {
  color: white
}

ul {
  list-style-type: none;
  display: flex;
  align-items: center;
  gap: 2rem;
}

img {
  display: block;
  max-width: 100%;
  height: auto;
}

li a {
  text-decoration: none;
  font-size: 1.2rem;
  font-weight: bold;
  color: white;
  transition: 0.4s;
}

li a:hover {
  text-decoration: underline;
}

.logo {
  display: flex;
  gap: 0.5rem;
  cursor: pointer;
}

.logo-text {
  color: white;
  display: flex;
  flex-direction: column;
  justify-content: center;
}

.big {
  font-size: 2rem;
  font-weight: bold;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  /* font-family: 'Madimi One', 'sans-serif'; */
}

 @media screen and (max-width: 880px) {
  ul {
    display: none;
  }
 }

</style>