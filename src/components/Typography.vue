<script setup>
const props = defineProps({
  heading: { type: Number, default: 'h1' }
})
const headingSize = props.heading;
</script>

<template>
  <h1 v-if="headingSize === 1"><slot /></h1>
  <h2 v-if="headingSize === 2"><slot /></h2>
  <h3 v-if="headingSize === 3"><slot /></h3>
  <h4 v-if="headingSize === 4"><slot /></h4>
  <h5 v-if="headingSize === 5"><slot /></h5>
  <h6 v-if="headingSize === 6"><slot /></h6>
</template>
<style scoped lang="scss">
  h1{ font-size: 2rem; }
  h2{ font-size: 1.75rem; }
  h3{ font-size: 1.5rem; }
  h4{ font-size: 1.15rem; text-transform: uppercase; }
  h5{ font-size: 1rem; }
  h6{ font-size: 0.85rem; }
</style>
<script>
// If you are using PurgeCSS, make sure to whitelist the carousel CSS classes

export default {
  name: 'Typography'
};
</script>