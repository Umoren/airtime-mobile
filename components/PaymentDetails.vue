<template>
  <div class="">
    <form action="" class="mt-5 horix" v-on:submit.prevent>
      <div class="mb-4">
        <label for="Mobile Network">Mobile Number<sup class="text-danger">*</sup> </label>
        <input class="form-control" v-model="data.PhoneNumber" placeholder="08171942286" type="number" min="11" required/> 
      </div>

      <div class="mb-4"> 
        <label for="Select network"> Select Network<sup class="text-danger">*</sup> </label>
        <select class="form-control" v-model="data.Code" required> 
          <option value="MTN" >
            MTN Nigeria 
          </option>

           <option value="Airtel">
            Airtel Nigeria
          </option>

           <option value="GLO">
            Glo Nigeria
          </option>

           <option value="9mobile">
            9Mobile
          </option>
        </select>
      </div>

      <div>
        <label for="amount"> Amount <sup class="text-danger">*</sup></label>
         <div class="input-group mb-2">
            <div class="input-group-prepend">
              <div class="input-group-text">N</div>
            </div>
            <input type="number" v-model="data.Amount" class="form-control" id="inlineFormInputGroup" placeholder="Amount" required>
         </div>
      </div>

      <div style="height: 10rem"> </div>
      <footer class="d-flex justify-content-center">
        <button @click="handleWallet" class="button--wallet"> 1-Touch with E-wallet 
        <arrow-right-icon size="1x" class="custom-class"></arrow-right-icon>
        </button>
      </footer>
    </form>
  </div>
</template>

<script>
import { ArrowRightIcon } from 'vue-feather-icons'
export default {
  components : {
    ArrowRightIcon
  },

  data() {
    return {
      data: {
        Code: '',
        Amount: '',
        PhoneNumber: ''
        
      }
    }
  },
 
  methods : {
    handleWallet() {
      const requestObject = {
        network: this.data.Code,
        amount: this.data.Amount,
        phone: this.data.PhoneNumber,
        SecretKey: "hfucj5jatq8h"
      }

      const headers = {
         'Content-Type': 'application/json',
          'Authorization': "Bearer uvjqzm5xl6bw"
      }
      this.$axios
        .post('https://cors-anywhere.herokuapp.com/', 'https://sandbox.wallets.africa/bills/airtime/purchase', requestObject, {headers})
        .then(response => {
          console.log(response.data)
        })
        .catch(err => console.error(err))
    },

    
  }
  
}
</script>

<style scoped>
  .button--wallet{
    padding: 10px  !important;
  }

  @media (min-width: 700px) {
    .horix{
      width: 50%;
      height: 50%;
      position: absolute;
      left: 0;
      top: 50px;
      bottom: 50px;
      right: 0;
      margin: auto;
    }
  }
</style>