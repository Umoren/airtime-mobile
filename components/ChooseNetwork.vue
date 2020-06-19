<template>
  <div class="row">
    <div class="struc ">
       <img class="shadow card-img" src="/networks/MTN Logo.svg" alt=" MTN Logo">
    </div>

    <div class=" struc">
        <img class="shadow card-img" src="/networks/Airtel Nigeria Logo.svg" alt=" MTN Logo">
      </div>

    <div class="struc">
         <img class="card-img shadow" src="/networks/Globacom Limited Logo.svg" alt=" MTN Logo">
     </div>

    <div class="struc">
      <img class="card-img shadow" src="/networks/9mobile Logo.svg" alt=" MTN Logo">
    </div>
  </div>
</template>

<style  scoped>

  .card{
        border: 0.10rem solid #eeeeee !important;
    border-radius: 0.33rem !important;
  }
  .card-img{
    padding: 1rem 1rem !important;
  }

  .struc{
    margin: auto;
    padding: 0;
    width: 45%;
    margin-top: 1rem;
    margin-bottom: 1rem;
  }

  @media(min-width: 700px){
    img{
      height: 15rem;
      width: 15rem;
    }

    .struc{
      width: auto;
    }
  }
</style>

