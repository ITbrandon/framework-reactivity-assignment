<script setup>
import ButtonComponent from './ButtonComponent.vue';
import GalleryButtons from './GalleryButtons.vue';
import NavBar from './NavBar.vue';
import {ref, computed} from 'vue';

const props = defineProps({
  links: {
    type: Array,
    required: true
  },
  data: {
    type: Array,
    required: true
  }
})
let indexNumber = ref(0)
let interval;

//Handles The Emitted Data from the Gallery Buttons
const pageHandler = (index) => {
    indexNumber.value = index;
    resetTimer();
}

const slideChange = () => {
interval = setInterval(() => {
    indexNumber.value = (indexNumber.value + 1) % props.data.length;
  },5000)
}

slideChange();


const text = computed(() => {
 return props.data[indexNumber.value].headerText
})
const buttonText = computed(() => {
 return props.data[indexNumber.value].buttonText
})
const bannerImage = computed(() => {
 return `banner${indexNumber.value}`
})

const resetTimer = () => {
    clearInterval(interval)
    slideChange();
  }

</script>

<template>

<header :class="bannerImage">
  <NavBar :links="props.links" />
  <section>
  <h2>{{ text }}</h2>
  <ButtonComponent>
    {{ buttonText }}
  </ButtonComponent>
  <GalleryButtons :data="data" @changePage="pageHandler"/>
  </section>
</header>

</template>

<style scoped>

header {
  height: 115vh;
  background-size: cover;
  background-position: center; 
  background-repeat: no-repeat;
}

.banner0 {
  background-image: url(../assets/banner1.jpg);
}

.banner1 {
  background-image: url(../assets/banner2.jpg);
}

.banner2 {
  background-image: url(../assets/banner3.jpg);
}

.banner3 {
  background-image: url(../assets/banner4.jpg);
}

h2 {
  font-size: 1.6rem;
  text-align: center;
  color: white;
  position: absolute;
  top: 84%;
  left: 50%;
  transform: translate(-50%, -50%);
}

@media screen and (max-width: 880px) {
  h2 {
    font-size: 1.2rem
  }
 }

</style>