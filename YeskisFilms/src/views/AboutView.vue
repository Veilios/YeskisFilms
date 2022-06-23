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
      <div>
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
  </div>
</template>

<script>

export default {
  name: 'about',
  props: ['lang'],
}
</script>

<style>
@media (min-width: 1024px) {

  .about {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 95vh;
    font-family: 'EB Garamond', serif;
  }

  .frame {
    width: 275px;
    height: 380px;
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
  }

  .headshot {
    width: 80%;
    height: 75%;
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
    width: 30%;
    height: 65vh;
    display: flex;
    flex-direction: column;
    padding: 0 7rem 0 2rem;
    justify-content: flex-start;
    align-items: flex-start;
  }

  .b_title {
    font-style: italic;
    font-weight: 700;
  }

  .b_text {
    font-weight: 500;
  }

  .socials {
    padding-top: 4rem;
    width: 100%;
    display: flex;
    justify-content: space-evenly;
  }

  .socials img {
    height: 2rem;
  }

  .socials img:hover {
    transform: scale(1.3);
    transition: ease-in 0.5s;
  }
}
</style>
