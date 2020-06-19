<template>
  <div>
    <header class="container">
      <nav class="row m-auto mt-3 p-2">
         <nuxt-link to="/">
           <arrow-left-icon size="2x" class="custom-class"></arrow-left-icon>
          </nuxt-link>
        <h3 class="m-auto"> Airtime top up</h3>
      </nav>
    </header>

    <section class="container mt-3">
      <h3> Available Networks </h3>

      <ChooseNetwork />

    </section>

    <div style="height: 10rem"> </div>
    <footer class="d-flex justify-content-center container">
      <nuxt-link to="/details" class="button--wallet"> Continue 
       <arrow-right-icon size="1x" class="custom-class"></arrow-right-icon>
      </nuxt-link>
    </footer>
  </div>
</template>

<script>
import ChooseNetwork from '~/components/ChooseNetwork'
import { ArrowLeftIcon, ArrowRightIcon } from 'vue-feather-icons';
export default {
  components: {
    ChooseNetwork,
    ArrowLeftIcon,
    ArrowRightIcon
  }
}
</script>


<style  scoped>
  h5{
    font-weight: 500;
    line-height: 1.5;
    letter-spacing: 1px;
    white-space: normal;
  }
</style>
