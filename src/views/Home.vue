<template>
  <div class="container p-3">
    <div class="row d-flex flex-column justify-content-center p-3 text-center border-bottom">
      <h2>Real news, curated by real humans</h2>
      <h5 class="text-muted">Packed with the trends, news and links you need to be smart, informaed, and a head of the curve.</h5>
      <hr>
    </div>
    <div class="row mt-5">
        <card v-for="newsletter in lists" :key="newsletter.id" :card_newsletter="newsletter"></card>
    </div>
    <div class="row d-flex flex-column justify-content-center p-3 mt-5 text-center border-bottom">
      <h2>Up and coming</h2>
      <h6 class="text-muted">
        if these newsletters reach their goals (or get <a href="#">sponsorship</a>), well bring on expert writers and launch them.
        Vote for all your favorites:
      </h6>
    </div>
    <div class="row mt-5">
        <CardVote v-for="newsletter in upComing" :key="newsletter.id" :card_newsletter="newsletter"></CardVote>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from '@/components/card.vue'
import CardVote from '@/components/cardVote.vue'

import axios from 'axios'

export default {
  name: 'home',
  components: {
    Card,
    CardVote
  },
  created () {
    this.getTags();
  },
  data(){
    return {
      lists : [],
      upComing : []
    }
  },
  methods: {
       async getTags ()  {
        let url = process.env.VUE_APP_URL_API_NEWSLETTER;
        let resp = await axios.get(url)
        let newsletter = resp.data; 
        this.lists = newsletter.filter( ele => { return (ele.subscribed > ele.target )});
        this.upComing = newsletter.filter( ele => { return (ele.subscribed < ele.target )});
        // eslint-disable-next-line no-console
        console.log(resp.data)
      }
  }
}
</script>

<style>
  .border-bottom{
    border-bottom: 5px solid gray;
  }
</style>
