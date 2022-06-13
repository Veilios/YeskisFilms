<template>
  <div class="about">
    <div class="frame">
      <img class="headshot" src="colin-lloyd-UOBgu1hEj0o-unsplash.jpg" alt="Headshot of Fernando R. Cruz" />
      <h3 class="f_name">Fernando R. Cruz</h3>
    </div>

    <div class="bio">
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

      <div class="socials">
        <a href="">
          <img src="youtube.png" />
        </a>
        <a href="">
          <img src="instagram.png" />
        </a>
        <a href="">
          <img src="facebook.png" />
        </a>
      </div>
    </div>
  </div>
</template>

<style>
@media (min-width: 1024px) {

  .about {
    display: flex;
    justify-content: center;
    align-items: center;
    color: #FFFFFF;
    height: 95vh;
  }

  .frame {
    width: 275px;
    height: 380px;
    left: 204px;
    top: 230px;
    background: #FFF;
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
    font-style: normal;
    font-weight: 400;
    color: #444;
    padding-top: 0.3rem;
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
    font-style: normal;
    font-weight: 400;
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
