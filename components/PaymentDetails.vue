<template>
  <div class="">
    <form action="" class="mt-5 horix">
      <div class="mb-4">
        <label for="Mobile Network">Mobile Number<sup class="text-danger">*</sup> </label>
        <input class="form-control" placeholder="08171942286" type="number" min="0" max="13" required/> 
      </div>

      <div class="mb-4"> 
        <label for="Select network"> Select Network<sup class="text-danger">*</sup> </label>
        <select class="form-control" required> 
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
            <input type="number" class="form-control" id="inlineFormInputGroup" placeholder="Amount" required>
         </div>
      </div>

      <div style="height: 10rem"> </div>
      <footer class="d-flex justify-content-center">
        <nuxt-link to="/details" class="button--wallet"> 1-Touch with E-wallet 
        <arrow-right-icon size="1x" class="custom-class"></arrow-right-icon>
        </nuxt-link>
      </footer>
    </form>
  </div>
</template>

<script>
import { ArrowRightIcon } from 'vue-feather-icons'
export default {
  components : {
    ArrowRightIcon
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