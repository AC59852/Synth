<template>
  <section>
      <swiper
        :modules="modules"
        :slides-per-view="1"
        :space-between="0"
        :pagination="{ clickable: true }"
        :loop="true"
        class="hero__wrapper"
      >
        <swiper-slide 
          v-for="slide in sliderData" 
          :key="slide.id" 
          :style="{ background: `linear-gradient(rgba(0, 0, 0, 0.3), rgba(0, 0, 0, 0.3)), url('/imgs/${slide.img}')`}"
          class="hero__slide"
        >
        <h2 class="hero__heading">{{ slide.heading }}</h2>
        </swiper-slide>
      </swiper>
  </section>
</template>

<script>
 import { Pagination, A11y } from 'swiper';

  // Import Swiper Vue.js components
  import { Swiper, SwiperSlide } from 'swiper/vue';

  // Import Swiper styles
  import 'swiper/css';
  import 'swiper/css/pagination';

  // Import Swiper styles
  export default {
    data() {
      return {
        sliderData: [
          {id: 0, heading: "Feel the Difference", img: 'hero_placeholder.jpg'},
          {id: 1, heading: "slide 2", img: 'hero_placeholder.jpg'},
          {id: 2, heading: "slide 3", img: 'hero_placeholder.jpg'},
          {id: 3, heading: "slide 4", img: 'hero_placeholder.jpg'},
        ],
      }
    },

    setup() {
      return {
        modules: [Pagination, A11y],
      };
    },

    components: {
      Swiper,
      SwiperSlide,
    },
  };
</script>

<style>

</style>