<template>
  <div class="card">
    <div class="image">
      <img :src="require(`@/static/${card.image}`)" alt="" />
    </div>
    <div class="text">
      <h3>{{ card.title }}</h3>
      <p>{{ card.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["card"],
};
</script>

<style scoped>
.card {
  width: 90vw;
  height: 50vw;
  border: 1px solid var(--main-black);
  display: flex;
  justify-content: center;
  align-items: center;
  background: var(--main-bronze);
  box-shadow: 5px 5px 5px 0 black;
  border: 0.5vw solid var(--main-black);
  color: var(--main-black);
}
.image,
.text {
  width: 50%;
  height: 100%;
}
.text {
  padding: 1vw;
  overflow-y: scroll;
}
.text > h3 {
  margin-bottom: 1vw;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
::-webkit-scrollbar {
  width: 5px; /* Remove scrollbar space */
  background: transparent; /* Optional: just make scrollbar invisible */
}
/* Optional: show position indicator in white */
::-webkit-scrollbar-thumb {
  background: var(--main-white);
}
@media screen and (min-width: 700px) {
  .card {
    width: 46vw;
    height: 25vw;
  }
}
</style>
