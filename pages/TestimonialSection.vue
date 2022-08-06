<template>
  <div class="testimonials-section">
    <h2>Testimonials</h2>
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
import { defineComponent } from 'vue'
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
      ],
      async mounted() {
        await this.$nextTick()
        /* eslint-disable */
        new Swiper(this.$refs.carousel)
      },
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
</style>
