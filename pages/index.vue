<template>
  <div class="container">
    <div>
      <img src="/wallet.svg" id="wallet" alt="wallet">
      <h2 class="title">
        Mobile Airtime
      </h2>
      <div class="links">
        <!-- <a
          href="https://nuxtjs.org/"
          target="_blank"
          rel="noopener noreferrer"
          class="button--wallet"
        >
          Buy Airtime
        </a> -->

        <nuxt-link to="/providers" class="button--wallet"> Buy Airtime</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>

export default {

}
</script>

<style  scoped>

.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

@media (max-width: 360px){
  .button--wallet{
    width: 90%;
  }
}


#wallet {
    width: 20rem;
    height: 20rem;
}

.title {
  font-family:
    'Karla',
    sans-serif;
  display: block;
  font-weight: 600;
  font-size: 3rem;
  color: #35495e;
  letter-spacing: 0px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
