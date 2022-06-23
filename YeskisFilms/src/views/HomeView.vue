<template>
  <div class="Home" id="home">
    <transition class="fade">
      <h1>Yeskis Films</h1>
    </transition>
  </div>
</template>

<style>
.Home {
  width: 100%;
  height: 90vh;
  display: flex;
  justify-content: center;
}

h1 {
  display: flex;
  align-items: center;
  animation: fadeIn 5s;
  -webkit-animation: fadeIn 5s;
}

@keyframes fadeIn {
  0% {
    opacity: 0;
  }

  100% {
    opacity: 1;
  }
}

@media (max-width:992px) {
  .Home{
    height: 100vh;
  }
}
</style>