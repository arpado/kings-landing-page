<template>
  <div class="hero-section">
    <div class="hero-text">
      <h1>Visit the City Where Kings Land!</h1>
      <h2>Unbealivable Offers All Year Until Winter Comes!</h2>
    </div>
    <button class="call-to-action" @click="$emit('booking-request')">BOOK NOW!</button>
  </div>
</template>

<script>
export default {};
</script>

<style>
.hero-section {
  width: 100%;
  height: 100vh;
  background-color: var(--main-bronze);
  background-image: url("@/static/game-of-thrones-red-keep-cr-hbo.webp");
  background-size: cover;
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
}
h1 {
  font-size: 2.5rem;
}
h2 {
  font-size: 1.5rem;
}
.hero-text {
  position: initial;
  height: 60%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  color: var(--main-black);
  text-align: center;
}
.call-to-action {
  position: absolute;
  top: 80%;
  left: 50wv;
  width: 200px;
  height: 50px;
  background-color: var(--main-black);
  color: var(--main-white);
  font-family: "Cormorant Upright", serif;
  font-weight: bold;
  font-size: 1.5rem;
  cursor: pointer;
}
@media screen and (min-width: 650px) {
  .hero-text {
    position: absolute;
    bottom: 50%;
    left: 50%;
    height: initial;
    width: initial;
    text-align: start;
  }
  h1 {
    font-size: 4rem;
  }
  h2 {
    font-size: 2rem;
  }
}
</style>
