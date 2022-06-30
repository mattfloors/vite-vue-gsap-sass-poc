<template>
  <div id="fancy-page">
    <img ref="logo" :src="logoImg" alt="Logo" width="210" height="210">
    <Circle :color="colors.blue" />
    <Circle :color="colors.red" />
    <Circle :color="colors.yellow" />
    <Circle :color="colors.green" />
    <Circle :color="colors.purple" />
    <Circle :color="colors.pink" />
    <CarouselVue></CarouselVue>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from 'gsap';
// @ts-ignore
import logoImg from './assets/logo.png';
import Circle from "./components/Circle.vue";
import CarouselVue from "./components/Carousel.vue";

const logo = ref(null);
let tl = null;

const colors = {
  brand: '#42b983',
  blue: '#0277bd',
  red: '#c62828',
  yellow: '#ffeb3b',
  purple: '#6a1b9a',
  green: '#43a047',
  pink: '#ff80ab',
}

onMounted(() => {
  tl = gsap.timeline();

  tl.from(logo.value, {
    x: -300,
    backgroundColor: colors.yellow,
    border: `5px solid ${colors.pink}`,
    duration: 3,
    rotation: 40,
    ease: "bounce",
  });

  tl.from(
    ".circle",
    {
      y: "random(-200, 200)",
      opacity: 0,
      duration: 1,
      stagger: 0.15,
    },
    "+=1"
  );
});
</script>

<style scoped lang="scss">
#fancy-page {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  align-items: center;
  justify-content: center;

  img {
    border: 5px solid v-bind('colors.brand');
    border-radius: 100%;
  }
}

@media (max-width: 600px) {
  #fancy-page {
    flex-direction: column;
  }
}
</style>
