<template>
  <div class="testimonials-section">
    <h2>Testimonials</h2>
    <!-- <carousel class="carousel" :settings="settings" :breakpoints="breakpoints">
      <slide v-for="(testimonial, index) in testimonials" :key="index">
        <TestimonialCard :testimonial="testimonial" />
      </slide>

      <template #addons>
        <navigation />
        <pagination />
      </template>
    </carousel> -->
    <!-- <client-only> -->
      <swiper
        ref="carousel"
        class="swiper"
        :slides-per-view="2"
        :space-between="50"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide
          v-for="(testimonial, index) in testimonials"
          :key="index"
          :options="{ spaceBetween: 20 }"
        >
          <TestimonialCard :testimonial="testimonial" />
        </swiper-slide>
      </swiper>
    <!-- </client-only> -->
  </div>
</template>

<script>
// https://codesandbox.io/s/qlvlg
// :items-to-show="3"
// import "vue3-carousel/dist/carousel.css";
import { defineComponent } from 'vue'
// import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
// Import Swiper Vue.js components
// import { Swiper, SwiperSlide } from 'swiper/vue'

// Import Swiper styles
// import 'swiper/css'
import { Swiper, SwiperSlide } from 'swiper/swiper-bundle.min'
import 'swiper/swiper-bundle.min.css'

import TestimonialCard from '../components/TestimonialCard.vue'

export default defineComponent({
  name: 'TestimonialSection',
  components: {
    // Carousel,
    // Slide,
    // Pagination,
    // Navigation,
    TestimonialCard,
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      testimonials: [
        {
          name: 'Sandor Clegane',
          text:
            "I left this shit city cause I didn't wanna die it in. Am I gonna die in this shit city?",
          profilePic: 'SandorClegane.webp',
        },
        {
          name: 'Sansa Stark',
          text:
            "Growing up at Winterfell, all I ever wanted was to escape, to come here, to the capital. To see the southern knights and their painted armor, and King's Landing after dark. All the candles burning in all those windows...",
          profilePic: 'QueenSansa.PNG.webp',
        },
        {
          name: 'Olenna Tyrell',
          text: 'Oh! You can smell the shit from five miles away.',
          profilePic: 'OlennaS7E3.webp',
        },
        /* {
          name: 'Sansa Stark',
          text:
            "Growing up at Winterfell, all I ever wanted was to escape, to come here, to the capital. To see the southern knights and their painted armor, and King's Landing after dark. All the candles burning in all those windows...",
          profilePic: 'QueenSansa.PNG.webp',
        }, */
      ],
      async mounted() {
        await this.$nextTick()
        /* eslint-disable */
        new Swiper(this.$refs.carousel)
      },
      // settings: {
      //   itemsToShow: 1,
      //   // snapAlign: "center",
      //   wrapAround: true,
      // },
      // breakpoints: {
      //   700: {
      //     itemsToShow: 3,
      //     // snapAlign: "center",
      //     wrapAround: true,
      //   },
      // },
    }
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper)
    }
    const onSlideChange = () => {
      console.log('slide change')
    }
    return {
      onSwiper,
      onSlideChange,
    }
  },
})
</script>

<style scoped>
h2 {
  color: var(--main-white);
  font-size: 2rem;
  font-weight: bold;
  display: block;
}
.testimonials-section {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  background-color: var(--main-brown);
}
.swiper {
  width: 100%;
  max-width: 1400px;
  height: 550px;
  overflow: hidden;
  display: flex;
  justify-content: space-evenly;
}
/*.carousel > :first-child {
  height: 550px;
}*/
/*carousel preset */
/*.carousel__slide > .card {
  transform: scale(1);
  opacity: 0;
  transition: 1s;
}
.carousel__slide--visible > .card {
  opacity: 1;
  transform: scale(1);
}
.carousel__slide--next > .card {
  transform: scale(0.7) translate(-10px);
}
.carousel__slide--prev > .card {
  transform: scale(0.7) translate(10px);
}*/
/* .carousel__slide--active > .card {
  transform: scale(1);
  z-index: 1;
} */
/*.carousel__icon {
  background: var(--main-black);
} */
</style>

<style>
/* .carousel__prev,
.carousel__next {
  box-sizing: border-box;
  border: 1px solid white;
  background-color: var(--main-black);
  width: 3rem;
  height: 3rem;
  border-radius: 0;
  font-size: 2rem;
}
.carousel__prev {
  left: 10px;
}
.carousel__next {
  right: 10px;
}
.carousel__pagination-button {
  background-color: var(--main-black);
}
.carousel__pagination-button--active {
  background-color: var(--main-white);
} */
</style>
