<template>
  <div class="about" id="about">

    <div class="frame">
      <img class="headshot" src="../assests/headshot.jpg" alt="Headshot of Fernando R. Cruz" />
      <h3 class="f_name">Fernando R. Cruz</h3>
    </div>

    <div class="bio" v-if="this.lang === 'En'">
      <div>
        <h2 class="b_title">Driven by Creativity and Love</h2>

        <p class="b_text">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
          magna aliqua.
          Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
          Duis
          aute irure dolor in reprehenderit in
          voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
          sunt in culpa qui officia deserunt mollit
          anim id est laborum.
        </p>
      </div>
    </div>

    <div class="bio" v-if="this.lang === 'Es'">
      <h2 class="b_title">Inspirado por Creatividad y Amor</h2>

      <p class="b_text">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et
        dolore
        magna aliqua.
        Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.
        Duis
        aute irure dolor in reprehenderit in
        voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
        sunt in culpa qui officia deserunt mollit
        anim id est laborum.
      </p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'about',
  props: ['lang'],
}
</script>

<style>
.about {
  display: flex;
  justify-content: center;
  font-family: 'EB Garamond', serif;
}

.frame {
  width: 17.18rem;
  height: 22.5rem;
  left: 204px;
  top: 230px;
  background: #FFF;
  box-shadow: 0 0 10px 5px gray;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  margin-left: 5rem;
  border-radius: 3px;
  align-self: center;
}

.headshot {
  width: 80%;
  height: auto;
  background: #FFFFFF;
  object-fit: cover;
  margin-top: 1rem;
  border-radius: 2px;
}

.f_name {
  font-family: 'Smooch', cursive;
  font-weight: 400;
  padding-top: 0.3rem;
  font-size: 1.5rem;
}

.bio {
  width: 35%;
  height: 80vh;
  display: flex;
  flex-direction: column;
  padding: 0 7rem 0 2rem;
  justify-content: center;
}

.b_title {
  font-style: italic;
  font-weight: 700;
}

.b_text {
  font-weight: 500;
}

@media (max-width:992px) {
  .about {
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 0 20px;
    height: 100vh;
    margin-top: 3rem;
  }

  .frame {
    left: 0;
    margin: 0;
  }

  .bio {
    width: auto;
    justify-content: center;
    align-items: center;
    padding: 0 0.5rem;
  }
}
</style>
