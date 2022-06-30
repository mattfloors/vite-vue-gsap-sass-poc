<template>

  <div class="card">
    <div class="card-header">
      <Typography :heading="1"
        data-aos="fade-up"
        data-aos-offset="200"
        data-aos-easing="ease-in-out">
        Card Header
      </Typography>
    </div>
    <div class="card-body">
      <p 
        data-aos="zoom-in"
        data-aos-offset="200"
        data-aos-easing="ease-in-out">
        {{msg}}
    </p>
    </div>
  </div>

</template>

<script>
import { onMounted } from "@vue/runtime-core";
import Typography from "./Typography.vue";
import AOS from "aos";
export default {
  name: "Card",
  props: {
    msg: String,
  },
  components: {Typography},
  setup() {
    onMounted(() => {
      console.log('aaaa')
      AOS.init();
    });
  },
};

</script>