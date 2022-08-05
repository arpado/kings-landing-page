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
      <!--<ul v-show="menuVisible">
        <li v-for="(navLink, index) in navArray" :key="index">
          {{ navLink.text }}
        </li>
      </ul>-->
    </nav>
  </header>
</template>

<script>
//  v-show="innerWidth < 1000" @click="toggleMenu"
import DropdownMenu from '@/components/DropdownMenu.vue'
import HorizontalMenu from '@/components/HorizontalMenu.vue'

export default {
  components: { DropdownMenu, HorizontalMenu },
  // props: ['innerWidth'],
  // emits: ['scrollRequest'],
  data() {
    return {
      navArray: [
        { text: 'Home', sectionId: 'hero-section' },
        { text: 'Testimonials', sectionId: 'testimonials' },
        { text: 'About Us', sectionId: 'about-us' },
        { text: 'Points of Interest', sectionId: 'points-of-interest' },
        { text: 'Contact', sectionId: 'contact' },
      ],
      // isWideScreen: true,
      menuVisible: false,
      // payload: String
      // listeners: [],
      // screenSize: this.window.innerWidth,
    }
  },
  created() {
    // this.checkScreenSize();
  },
  mounted() {
    // this.checkScreenSize();
    // window.addEventListener('resize', this.checkScreenSize)
    window.addEventListener('click', this.closeOpenNavMenu)
    // (e) => {
    //   console.log(this.menuVisible);
    //   if (
    //     this.menuVisible &&
    //     this.innerWidth < 1100 &&
    //     !e.target.classList.contains("hamburger")
    //   ) {
    //     this.menuVisible = false;
    //   }
    // });
    // this.listeners.push(resizeHandler);
    // this.listeners.push(clickHandler);
  },
  unmounted() {
    // for (handler in this.listeners) {
    //   console.log(handler);
    //   window.removeEventListener(handler);
    // }
    // window.removeEventListener('resize', this.checkScreenSize)
    window.removeEventListener('click', this.closeOpenNavMenu)
  },
  methods: {
    reload() {
      window.location.reload(true)
    },
    // checkScreenSize() {
    //   // if (this.innerWidth < 1100) {
    //   //   // console.log(this.innerWidth);
    //   //   // console.log(this.menuVisible);
    //   //   // return !this.menuVisible;
    //   //   this.isWideScreen = false;
    //   // } else {
    //   //   // return this.menuVisible;
    //   //   this.isWideScreen = true;
    //   // }
    //   // console.log(this.innerWidth);
    //   this.isWideScreen = window.innerWidth >= 1100
    // },
    toggleMenu() {
      this.menuVisible = !this.menuVisible
    },
    closeOpenNavMenu(e) {
      // console.log(this.menuVisible);
      if (
        this.menuVisible &&
        // window.innerWidth < 1100 &&
        !e.target.classList.contains('hamburger')
      ) {
        this.menuVisible = false
      }
    },
    emitScrollRequest(id) {
      this.$emit('scroll-request', id)
    },
  },
  // itt meg kell oldani h a menu zaruljon resizenal
  // computed: {
  //   closeMenu() {
  //     if (window.innerWidth > 1100) {
  //       return !this.menuVisible
  //     }
  //   },
  // },
  // computed: {
  //   checkScreenSize() {
  //     console.log(screenSize);
  //     if (screenSize < 1100) {
  //       // console.log(this.innerWidth);
  //       // console.log(this.menuVisible);
  //       // return !this.menuVisible;
  //       // this.isWideScreen = false;
  //       return !this.isWideScreen;
  //     } else {
  //       // return this.menuVisible;
  //       // this.isWideScreen = true;
  //       return this.isWideScreen;
  //     }
  //     // console.log(this.innerWidth);
  //   },
  // },
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
/*ul {
  position: absolute;
  right: 5vw;
  top: 10vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  list-style: none;
  background: var(--main-brown);
  box-shadow: 5px 5px 5px 0 black;
}
li {
  margin: 1vw 2vw;
  overflow: hidden;
  position: relative;
}
li::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: -100%;
  width: 100%;
  height: 0.1em;
  background-color: var(--main-bronze);
  opacity: 0;
  transition: opacity 300ms, transform 300ms;
}
li:hover,
li:focus {
  cursor: pointer;
}
li:hover::after,
li:focus::after {
  opacity: 1;
  transform: translate3d(100%, 0, 0);
}*/
.hamburger {
  display: block;
  visibility: visible;
  margin-right: 10vw;
}
.hamburger:hover,
.hamburger:focus {
  cursor: pointer;
}
/* .hamburger:hover,
.hamburger:focus {
  box-shadow: 0 0 10px 10px white;
} */
.hidden {
  display: none;
  visibility: hidden;
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
  /*.hamburger {
    display: none;
    visibility: hidden;
  }*/
  /*ul {
    position: relative;
    flex-direction: row;
    right: unset;
    top: unset;
    display: flex;
    justify-content: space-between;
    align-items: center;
    list-style: none;
    color: var(--main-bronze);
    font-size: 2rem;
    box-shadow: unset;
  }
  li {
    margin-left: 30px;
    overflow: hidden;
    position: relative;
  }*/
}
</style>
