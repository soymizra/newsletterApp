<template>
<div class="col-sm-12 col-md-3">
  <div class="card mb-3 text-center" style="">
    <div class="card-body">
      <div style="width: 5rem; height: 5rem; display: inline-block; border-radius: 10rem; overflow:hidden">
        <img :src="card_newsletter.image" class="img-fluid" alt="">
      </div>
      <h4 class="card-title">{{ card_newsletter.title }}</h4>
      <p class="card-text text-muted">{{ card_newsletter.description }}</p>
      <button type="button" class="btn btn-outline-secondary btn-lg my-2 my-sm-0">
        <span class="large material-icons text-primary" style="font-weight: bold">email</span>
        Subscribe
      </button>
    </div>
  </div>
</div>
</template>
<script>
  export default {
    name: 'Card',
    props : [ 'card_newsletter' ]
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
