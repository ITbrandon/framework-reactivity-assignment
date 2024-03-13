<script setup>
import CarouselHeader from './components/CarouselHeader.vue';
const links = [
  {
    title: 'Our Story',
    href: 'https://www.miniclip.com/our-story'
  },

  {
    title: 'Games',
    href: 'https://www.miniclip.com/games'
  },

  {
    title: 'Web Games',
    href: 'https://www.miniclip.com/games/web'
  },

  {
    title: 'Careers',
    href: 'https://www.miniclip.com/careers/vacancies'
  },

  {
    title: 'Support',
    href: 'https://www.miniclip.com/support'
  }]

const carouselData = [
  {
    headerText: 'Play our most popular games now!',
    buttonText: 'PLAY NOW'
  },

  {
    buttonText: 'PLAY NOW'
  },

  {
    headerText: 'Be part of our family! We have new open positions',
    buttonText: 'SEE MORE'
  },

  {
    headerText: 'Wild football fun at your fingertips',
    buttonText: 'PLAY NOW'
  },
]
</script>

<template>
  <CarouselHeader :links="links" :data="carouselData"/>
</template>