<template>
  <div>
    <header class="container">
      <nav class="row m-auto mt-3 p-2">
         <nuxt-link to="/providers">
           <arrow-left-icon size="2x" class="custom-class"></arrow-left-icon>
          </nuxt-link>
           
        <h3 class="m-auto"> 
          <smartphone-icon size="1x" class="custom-class"></smartphone-icon>
          Buy Airtime
        </h3>
      </nav>
    </header>

      <section class="container mt-3">

       <PaymentDetails />

      </section>


  </div>  
</template>

<script>
import PaymentDetails from '~/components/PaymentDetails'
import { SmartphoneIcon, ArrowLeftIcon } from 'vue-feather-icons'

export default {
  components: {
    SmartphoneIcon,
    ArrowLeftIcon,
    PaymentDetails
  }
}
</script>



