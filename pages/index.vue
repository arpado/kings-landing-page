<template>
  <div id="app">
    <HeaderElement @scroll-request="scrollTo"/>
    <HeroSection id="hero-section" @booking-request="bookingRequest"/>
    <TestimonialSection id="testimonials" />
    <AboutUs  id="about-us" />
    <PointsOfInterest  id="points-of-interest"/>
    <ContactForm id="contact" />
  </div>
</template>

<script>
import VueScrollTo from 'vue-scrollto'

import HeaderElement from '@/components/HeaderElement.vue'
import HeroSection from '@/pages/HeroSection.vue'
import TestimonialSection from '@/pages/TestimonialSection.vue'
import AboutUs from '@/pages/AboutUs.vue'
import PointsOfInterest from '@/pages/PointsOfInterest.vue'
import ContactForm from '@/pages/ContactForm.vue'

export default {
  name: 'App',
  components: {
    HeaderElement,
    HeroSection,
    TestimonialSection,
    AboutUs,
    PointsOfInterest,
    ContactForm,
  },
  methods: {
    scrollTo(sectionId) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
            VueScrollTo.scrollTo(`#${sectionId}`, 300, { easing: 'linear' })
        }, 10)
      })
    },
    async bookingRequest() {
      await VueScrollTo.scrollTo('#contact')
      document.querySelector('#name').focus()
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  font-family: 'Cormorant Upright', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #9bf709;
}

p {
  font-size: 1.5rem;
}

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

:root {
  --main-brown: #9f3514;
  --main-bronze: #ae926d;
  --main-black: #402e32;
  --main-white: #fff;
}
</style>
