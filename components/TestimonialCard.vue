<template>
  <div class="card">
    <div class="profile-pic-box">
      <div class="profile-pic">
        <img
          :src="require(`@/static/profile-pics/${testimonial.profilePic}`)"
          alt=""
        />
      </div>
    </div>
    <div class="text">
      <p>{{ `"${testimonial.text}"` }}</p>
      <p>--{{ testimonial.name }}</p>
    </div>
    <div class="rating-box">
      <div class="raiting">* * * * *</div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["testimonial"],
};
</script>

<style scoped>
.card {
  width: 350px;
  height: 500px;
  padding: 20px;
  border: 1px solid black;
  background-color: var(--main-white);
  color: var(--main-black);
  box-shadow: 10px 10px 10px 0 black;
  display: grid;
  grid-template-rows: 1fr 2fr 1fr;
  grid-template-columns: 1fr;
}
.profile-pic-box {
  width: 100%;
  display: flex;
  justify-content: center;
}
.profile-pic {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  border: 1px solid black;
  background: var(--main-bronze);
  grid-row-start: 1;
  overflow: hidden;
}
.profile-pic > img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.text {
  width: 100%;
  grid-row-start: 2;
  text-align: left;
}
.text > :last-child {
  margin-top: 20px;
}
.rating-box {
  width: 100%;
  grid-row-start: 3;
  display: flex;
  justify-content: center;
  align-items: center;
}
.raiting {
  width: 200px;
  color: yellow;
  background-color: var(--main-black);
  text-align: center;
  font-size: 2rem;
  font-weight: bold;
  text-align: center;
}
</style>
