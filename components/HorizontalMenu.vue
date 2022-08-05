<template>
  <ul>
    <li v-for="(navLink, index) in navArray" :key="index" @click="emitScrollRequest(navLink.sectionId)">
      {{ navLink.text }}
    </li>
  </ul>
</template>

<script>
export default {
   /* eslint-disable */ 
  props: ['navArray'],
  methods: {
    emitScrollRequest(id) {
      this.$emit('scroll-request', id)
    }
  }
}
</script>

<style scoped>
/*@media (min-width: 1100px) {*/
ul {
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
  margin: 0 30px;
  overflow: hidden;
  position: relative;
}
li::after {
  content: '';
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
}
</style>
