
<template>

  <div id="fancy-page">
    <Typography :heading="1">Title</Typography>
    <Typography :heading="4">SubTitle</Typography>

    <CarouselVue></CarouselVue>

    <div>
      <img ref="logo" :src="logoImg" alt="Logo" width="210" height="210">

      <Circle :color="colors.blue" />
      <Circle :color="colors.red" />
      <Circle :color="colors.yellow" />
      <Circle :color="colors.green" />
      <Circle :color="colors.purple" />
      <Circle :color="colors.pink" />
    </div>

    <Card :msg="'Maecenas ut urna non neque pulvinar molestie sed sit amet tortor. Praesent a varius metus. Ut fermentum lectus in laoreet sodales. Duis consectetur hendrerit leo ac dictum. Cras condimentum volutpat risus vel dignissim. Quisque ornare, magna vel venenatis bibendum, mi arcu porttitor lorem, in ullamcorper leo nibh vitae nisl. Sed condimentum sapien vitae eros euismod sollicitudin. Nam eget gravida velit, nec semper libero. Etiam eros enim, finibus vel augue a, vehicula scelerisque elit. Aliquam erat volutpat. Phasellus vehicula, libero at auctor suscipit, risus nisi lacinia magna, sit amet cursus eros ante quis tortor. Nam quam arcu, ultricies sit amet nunc ullamcorper, hendrerit venenatis nibh. Sed at placerat lacus.'"></Card>
    <Card :msg="'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis sit amet arcu velit. Praesent imperdiet luctus tempor. In hac habitasse platea dictumst. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Fusce molestie ante non arcu sagittis eleifend. Quisque id tortor in ex scelerisque condimentum quis a nisi. Nullam bibendum neque id dui egestas pulvinar. Pellentesque malesuada blandit erat in pellentesque. Quisque rutrum magna ac quam vulputate, ac rhoncus velit euismod. Praesent sit amet volutpat lorem. Aenean convallis tellus nec dolor tempor, vitae porta lorem porttitor. Aenean et porttitor mauris, eu molestie ex. Donec metus sem, elementum id ipsum tincidunt, sollicitudin iaculis neque.'"></Card>
    <Card :msg="'Phasellus in efficitur lacus. Cras placerat blandit sapien, in venenatis magna rhoncus in. Donec vel ipsum in nisl condimentum accumsan. Pellentesque urna libero, dictum eget magna et, scelerisque eleifend orci. Nam sagittis ex facilisis mauris finibus, dignissim pulvinar nulla feugiat. Etiam non mi pretium, bibendum tortor at, porta neque. Nulla placerat, urna at elementum dapibus, nulla enim auctor magna, lobortis laoreet ante sem id massa. Quisque elementum leo ac orci commodo placerat. Nunc tempus rhoncus enim, sit amet posuere ante feugiat quis.'"></Card>
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from 'gsap';
// @ts-ignore
import logoImg from './assets/logo.png';
import Circle from "./components/Circle.vue";
import CarouselVue from "./components/Carousel.vue";
import Typography from "./components/Typography.vue";
import Card from "./components/Card.vue";

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
  flex-direction: column;
  h1{
    font-size: 4rem;
  }
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
