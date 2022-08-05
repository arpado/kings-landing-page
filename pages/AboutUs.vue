<template>
  <div class="about-us">
    <!--<div class="grid-box">-->
    <!--<div class="float-box">-->
    <div class="flex-box">
      <div class="section-1">
        <div id="pic-1" class="illustration-pic">
          <img src="@/static/kings-landing-from-sea.webp" alt="" />
        </div>
        <div>
          <h2>About Us</h2>
          <p id="text-1" class="text">
            King's Landing is the capital, and largest city, of the Six
            Kingdoms. Located on the east coast of Westeros in the Crownlands,
            just north of where the Blackwater Rush flows into Blackwater Bay
            and overlooking Blackwater Bay, King's Landing is the site of the
            Iron Throne and the Red Keep, the seat of the King of the Andals and
            the First Men (hence the name). It enjoys a warm climate and life
            there is luxurious for those that can afford it, although it is not
            without its slums such as Flea Bottom. The city is overpopulated and
            dangerous at the best of times, despite being policed by the City
            Watch.
          </p>
        </div>
      </div>
      <div class="section-2">
        <div id="pic-2" class="illustration-pic">
          <img src="@/static/red-keep-close.webp" alt="" />
        </div>
        <p id="text-2" class="text">
          King's Landing was founded by King Aegon I Targaryen, King of the
          Andals and the First Men. He established a small wooden fort atop the
          hill, named the Aegonfort in his honor, where his ships first landed
          from Dragonstone, and used this as a base for his campaign to conquer
          the continent. Having achieved his goal, he established the new
          capital on the site of his original fort. The city expanded rapidly
          under his descendants.[2] By the time of Robert's Rebellion, the city
          had a population of approximately half a million people.[3]
        </p>
      </div>
      <div class="sction-3">
        <div id="pic-3" class="illustration-pic">
          <img src="@/static/great-sept-exteriors-far.webp" alt="" />
        </div>
        <p id="text-3" class="text">
          King's Landing has suffered occasional attacks during its existence,
          most notably during the civil war known as Robert's Rebellion, when
          Lord Tywin Lannister betrayed King Aerys II Targaryen and ordered his
          army to brutally sack the city before turning it over to Robert
          Baratheon as a sign of fealty.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.about-us {
  width: 100%;
  /*height: 100vh;*/
  height: fit-content;
  position: relative;
  background: linear-gradient(
      180deg,
      var(--main-brown) 10%,
      rgba(0, 0, 0, 0) 10%
    ),
    linear-gradient(180deg, var(--main-black) 90%, var(--main-brown) 90%);
}
/*.grid-box {
  position: absolute;
  top: -10vh;
  width: 100%;
  height: 120%;
  display: grid;
  grid-template-rows: repeat(12, 1fr);
  grid-template-columns: repeat(12, 1fr);
}
.float-box {
  position: absolute;
  top: -3rem;
  width: 100%;
  height: fit-content;
}*/
/*
linear-gradient(180deg, var(--main-brown) 10%, rgba(0, 0, 0, 0) 10%), linear-gradient(180deg, var(--main-black) 90%, var(--main-brown) 90%)
 */
.flex-box {
  width: 100%;
  height: fit-content;
  display: flex;
  flex-direction: column;
}
img {
  width: 100%;
  height: 100%;
}
.illustration-pic {
  background-color: var(--main-bronze);
  display: flex;
  justify-content: center;
  align-items: center;
  border: 0.5vw solid var(--main-bronze);
  width: 50vw;
  aspect-ratio: 2;
  box-shadow: 5px 5px 5px 0 black;
  margin: 20px;
  /*height: 30vw;
  max-width: 800px;
  max-height: 400px;
  min-width: 400px;
  min-height: 200px;*/
}
#pic-1 {
  /* top: -10vh;
  right: calc(40% + 100px);
  width: 80vw;
  height: 50vw;
  max-width: 800px;
  max-height: 500px;
  min-width: 400px;
  min-height: 250px;
  grid-row: 1/5;
  grid-column: 2/7;*/
  transform: rotate(-2deg);
  float: left;
}
#pic-2 {
  /*top: 35vh;
  left: 50vw;
  grid-row: 4/9;
  grid-column: 7/13;*/
  transform: rotate(-5deg);
  float: right;
}
#pic-3 {
  /*top: 75vh;
  right: 40%;
  min-width: 1000px;
  grid-row: 9/13;
  grid-column: 1/7;*/
  transform: rotate(7deg);
  float: left;
}
h2 {
  color: var(--main-white);
  margin-top: 4vw;
  /*grid-row: 2/3;
  grid-column: 9/11;*/
}
.text {
  color: var(--main-white);
  padding: 5%;
  text-align: left;
}
#text-1 {
  /*grid-row: 3/4;
  grid-column: 7/13;*/
}
#text-2 {
  /*grid-row: 5/9;
  grid-column: 1/7;*/
}
#text-3 {
  /*grid-row: 9/13;
  grid-column: 7/13;*/
}
</style>
