<template>
  <div id="app">
    <HeaderElement :inner-width="innerWidth" @scroll-request="scrollTo"/>
    <HeroSection id="hero-section" />
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
  data() {
    return {
      innerWidth: null,
      // sectionId: String,
    }
  },
  mounted() {
    window.addEventListener('resize', this.setInnerWidth)
    this.setInnerWidth()
    // this.logWindow();
  },
  unmounted() {
    window.removeEventListener('resize', this.setInnerWidth)
  },
  methods: {
    // logWindow() {
    //   console.log(window.innerWidth);
    // },
    setInnerWidth() {
      this.innerWidth = window.innerWidth
      // console.log(this.innerWidth);
    },
    scrollTo(sectionId /* to, , from, savedPosition */ ) {
      return new Promise((resolve, reject) => {
        setTimeout(() => {
          // if (sectionId.hash === sectionId) {
            VueScrollTo.scrollTo(`#${sectionId}`, 300, { easing: 'linear' })
          // }
        }, 10)
      })
    },
  },
  // computed: {
  //    setInnerWidth() {
  //     this.innerWidth = window.innerWidth;
  //   },
  // },
  // data() {
  //   return {
  //     innerWidth: window.innerWidth,
  //   },
  // },
  // computed: {
  //   consoleInnerWidth() {
  //     let result = window.addEventListener(()=> {

  //     }),
  //     this.innerWidth =
  //     console.log()
  //   },
  // },
  // mounted() {
  //   this.window.addEventListener("onresize", () => {
  //     console.log(this.window.innerWidth);
  //   });
  //   console.log("poop");
  // },
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
