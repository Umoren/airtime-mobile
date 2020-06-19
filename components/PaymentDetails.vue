<template>
  <div class="">
    <form action="" class="mt-5 horix" v-on:submit.prevent>
      <div class="mb-4">
        <label for="Mobile Network">Mobile Number<sup class="text-danger">*</sup> </label>
        <input class="form-control" id="phone-field" v-model="data.PhoneNumber" minlength="11" placeholder="08171942286" type="tel" min="11" required/>
      </div>

      <div class="mb-4">
        <label for="Select network"> Select Network<sup class="text-danger">*</sup> </label>
        <select class="form-control" id="network" v-model="data.Code" required>
          <option value="" disabled selected>Select Network </option>
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
            <input type="number" min="100" id="amount-field inlineFormInputGroup" v-model="data.Amount" class="form-control" placeholder="100" required>
         </div>
      </div>

      <div style="height: 10rem"> </div>
      <footer class="d-flex justify-content-center">
        <button @click="handleWallet"  class="button--wallet">
                   1-Touch with E-wallet
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

  watch: {
    amount(val) {
      if (val && this.errors.amount){
        this.errors.amount = null;
      }
    },

    phone(val) {
      if (val && this.errors.phone){
        this.errors.phone = null;
      }
    },

    network(val) {
      if (val && this.errors.network){
        this.errors.network = null;
      }
    }
  },

  errors: {
    handler(val) {
      if (val.amount) {
        document.getElementById('amount-field').classList.add('error');
      }

      if (val.phone) {
         document.getElementById('phone-field').classList.add('error');
      }

      if (val.network) {
         document.getElementById('network-field').classList.add('error');
      }
    }
  },


  methods : {

    validateInput(){
      if(isNaN(this.data.Amount) || this.data.Amount < 100)
        this.errors.amount = "The amount has to be N100 or more than that"

      if(isNaN(this.data.PhoneNumber) || this.data.PhoneNumber.length < 11)
        this.errors.phone = "Enter valid phone number"

      if(this.data.Code == "")
        this.error.network = "Please select a network";

      if(!this.errors.amount && !this.errors.phone)
        this.handleWallet()
    },

    handleWallet() {

      const requestObject = {
        Code: this.data.Code,
        Amount: this.data.Amount,
        PhoneNumber: this.data.PhoneNumber,
        SecretKey: "hfucj5jatq8h"
      }

      const headers = {
         'Content-Type': 'application/json',
          'Authorization': "Bearer uvjqzm5xl6bw"
      }

      var url = "https://sandbox.wallets.africa/bills/airtime/purchase"
      const proxyUrl = "https://cors-anywhere.herokuapp.com/"

      this.$axios
        .post(proxyUrl + url, requestObject, {headers})
           .then(response => {
             console.log(response.data)
             console.log(response.data.Message)

             swal({title: 'Transaction Completed!', text: 'N' + response.data.ResponseCode + ' naira ' + response.data.Message,  icon: 'success'})
            })
           .catch(err => {
             console.error(err)
              swal("Transaction Failed!", "Something is wrong", "error");

            })
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
