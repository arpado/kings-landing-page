<template>
  <div class="wrapper">
    <h2>Contacts</h2>
    <div class="contacts">
      <div class="location">
        <h3>Find Us!</h3>
        <div class="infos">
          <p>Adress: Kings Landing, Crownlands, Westeros</p>
          <p>Open: 7-22, Mon-Sun</p>
          <p>Telephone: (+12) 34/567 890</p>
          <p>Email: kings(at)landing.com</p>
        </div>
        <div class="map">
          <img src="@/static/kings-landing-map.jpg" alt="" />
        </div>
      </div>
      <div class="contact-form">
        <h3>Send a Message!</h3>
        <div class="form-wrapper">
          <div>
            <label for="name">Name:</label>
            <input id="name" type="text" name="name" />
          </div>
          <div>
            <label for="email">Email:</label>
            <input id="email" type="email" name="email" />
          </div>
          <div>
            <label for="message">Message:</label>
            <textarea
              id="message"
              name="message"
              cols="30"
              rows="10"
            ></textarea>
          </div>
        </div>
        <button>Send Message</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.wrapper {
  width: 100%;
  height: fit-content;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  background-color: var(--main-black);
  color: var(--main-white);
}
h2 {
  margin: 30px 0;
}
.contacts {
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: center;
  gap: 1rem;
}
.location,
.contact-form {
  height: 80vh;
  width: 80vw;
  padding: 1vw;
  /*display: flex;
  flex-direction: column;
  justify-content: space-around;
  align-items: flex-start;*/
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: repeat(12, 1fr);
  background: var(--main-brown);
  box-shadow: 5px 5px 5px 0 black;
}
h3 {
  align-self: center;
  margin: 20px 0;
  grid-row: 1/2;
  font-size: 1.5rem;
}
p {
  text-align: initial;
}
.infos {
  line-height: 2rem;
  grid-row: 2/6;
}
.map {
  align-self: center;
  justify-self: center;
  width: 100%;
  grid-row: 6/11;
  background: var(--main-bronze);
  border: 0.5vw solid var(--main-bronze);
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  max-height: 350px;
  max-width: 350px;
}
/*.map > img {
  width: 100%;
  height: 100%;
  object-fit: scale-down;
  border: 0.5vw solid var(--main-bronze);
}*/
.form-wrapper {
  grid-row: 2/10;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.form-wrapper > div {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  width: 100%;
}
label {
  font-size: 1.5rem;
}
input,
textarea {
  width: 100%;
  margin-top: 10px;
  font-size: 1.5rem;
}
input {
  height: 2rem;
}
button {
  grid-row: 11/12;
  margin: 0 auto;
  width: 200px;
  height: 50px;
  background-color: var(--main-black);
  color: var(--main-white);
  font-family: "Cormorant Upright", serif;
  font-weight: bold;
  font-size: 1.2rem;
  cursor: pointer;
}
@media screen and (min-width: 700px) {
  .wrapper {
    height: 100vh;
  }
  .contacts {
    flex-direction: row;
  }
  .location,
  .contact-form {
    width: 40vw;
  }
}
</style>
