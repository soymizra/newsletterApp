<template>
<div class="col-sm-12 col-md-3 col-lg-3">
  <div class="card mb-3 text-center" style="">
    <div class="card-header">Header</div>
    <div class="card-body">
      <div style="width: 5rem; height: 5rem; display: inline-block; border-radius: 10rem; overflow:hidden">
        <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR-ru4H-baek4AmbcYzV4KPpP3Ud64N9U5in1Mz59GO7VNpiz7Zhw" class="img-fluid" alt="">
      </div>
      <h4 class="card-title">Light card title</h4>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    </div>
  </div>
</div>
</template>
<script>
  export default {
    name: 'Card',
    data: () => ({

    })
  }
</script>
<style scoped>
  .card{
    border: none
  }
  .card-header{
    background-color: transparent;
  }
</style>
