<template>
  <header>
    <div class="logo" @click="reload">
      <img src="@/static/crown-logo.png" alt="" />
    </div>
    <nav>
      <HorizontalMenu
        class="widescreen-nav"
        :nav-array="navArray"
        @scroll-request="emitScrollRequest"
      />
      <div class="narrowscreen-nav">
        <div class="hamburger" @click="toggleMenu">Menu</div>
        <DropdownMenu
          v-show="menuVisible"
          :nav-array="navArray"
          @scroll-request="emitScrollRequest"
        />
      </div>
    </nav>
  </header>
</template>

<script>
import DropdownMenu from '@/components/DropdownMenu.vue'
import HorizontalMenu from '@/components/HorizontalMenu.vue'

export default {
  components: { DropdownMenu, HorizontalMenu },
  data() {
    return {
      navArray: [
        { text: 'Home', sectionId: 'hero-section' },
        { text: 'Testimonials', sectionId: 'testimonials' },
        { text: 'About Us', sectionId: 'about-us' },
        { text: 'Points of Interest', sectionId: 'points-of-interest' },
        { text: 'Contact', sectionId: 'contact' },
      ],
      menuVisible: false,
    }
  },
  mounted() {
    window.addEventListener('click', this.closeOpenNavMenu)
  },
  unmounted() {
    window.removeEventListener('click', this.closeOpenNavMenu)
  },
  methods: {
    reload() {
      window.location.reload(true)
    },
    toggleMenu() {
      this.menuVisible = !this.menuVisible
    },
    // the dropdown should be able to close if viewport goes wide enough, this should be solved later
    closeOpenNavMenu(e) {
      if (
        this.menuVisible &&
        // window.innerWidth > 1100 &&
        !e.target.classList.contains('hamburger')
      ) {
        this.menuVisible = false
      }
    },
    emitScrollRequest(id) {
      this.$emit('scroll-request', id)
    },
  },
}
</script>

<style scoped>
header {
  width: 100%;
  height: 10vh;
  padding-left: 2%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background-color: #9f3514;
  border: 1px solid black;
  box-shadow: 0 5px 5px 2px var(--main-black);
  position: fixed;
  color: var(--main-bronze);
  font-size: 2rem;
  z-index: 999;
}
.logo:hover,
.logo:focus {
  cursor: pointer;
}
.logo > img {
  max-width: 100px;
  max-height: 100px;
}
.hamburger {
  display: block;
  visibility: visible;
  margin-right: 10vw;
}
.hamburger:hover,
.hamburger:focus {
  cursor: pointer;
}
.widescreen-nav {
  display: none;
  visibility: none;
}
.narrowscreen-nav {
  display: flex;
  visibility: visible;
}

@media (min-width: 1100px) {
  .narrowscreen-nav {
    display: none;
    visibility: none;
  }
  .widescreen-nav {
    display: flex;
    visibility: visible;
  }
}
</style>
