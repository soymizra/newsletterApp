<template>
  <div class="container-fluid p-3">
    <div class="row d-flex flex-column justify-content-center p-4">
      <h2>Real news, curated by real humans</h2>
      <h5 class="text-muted">Packed with the trends, news and links you need to be smart, informaed, and a head of the curve.</h5>
    </div>
    <div class="row">
      <card></card>
      <card></card>
      <card></card>
      <card></card>
      <card></card>
      <card></card>
      <card></card>
      <card></card>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from '@/components/card.vue'

export default {
  name: 'home',
  components: {
    Card
  }
}
</script>
