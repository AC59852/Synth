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
          class="hero__slide"
        >
        <img class="hero__img" :src="'/imgs/' + slide.img" :alt="'Hero Img For ' + slide.heading">
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

  import '../sass/modules/_swiper.scss'

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