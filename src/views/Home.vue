<template>
  <div class="container p-3">
    <div class="row d-flex flex-column justify-content-center p-5 text-center">
      <h2>Real news, curated by real humans</h2>
      <h5 class="text-muted">Packed with the trends, news and links you need to be smart, informaed, and a head of the curve.</h5>
    </div>
    <div class="row">
      <div v-for="newsletter in lists" :key="newsletter.id">
        <card :card_newsletter="newsletter"></card>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Card from '@/components/card.vue'

import axios from 'axios'

export default {
  name: 'home',
  components: {
    Card
  },
  created () {
    this.getTags();
  },
  data(){
    return {
      lists : []
    }
  },
  methods: {
       async getTags ()  {
        let url = process.env.VUE_APP_URL_API_NEWSLETTER;
        let resp = await axios.get(url)
        this.lists = resp.data
        // eslint-disable-next-line no-console
        console.log(this.lists[0])
      }
  }
}
</script>
