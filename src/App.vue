<template>
  <div id="app">
      <nav id="nav" class="navbar navbar-expand-lg navbar-light p-3" style="border-bottom: solid rgba(0,0,0,.1) 1px">
        <a class="navbar-brand text-primary" style="font-weight: bold" href="#">[ INSIDE ]</a>
          <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarColor03" aria-controls="navbarColor03" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>

          <div class="collapse navbar-collapse" id="navbarColor03">
            <ul class="navbar-nav mr-auto">
              <li class="nav-item active">
                <router-link to="/" class="nav-link">Home</router-link>
              </li>
              <li class="nav-item">
                  <router-link to="/about" class="nav-link">About</router-link>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">Pricing</a>
              </li>
              <li class="nav-item">
                <a class="nav-link" href="#">About</a>
              </li>
            </ul>
            <form class="form-inline my-2 my-lg-0">
              <ComponentSearch></ComponentSearch>
              <button type="button" class="btn my-2 my-sm-0"> <i class="large material-icons text-primary" style="font-weight: bold">account_circle</i> </button>
              <button type="button" class="btn btn-outline-primary">SPONSORSHIP</button>
            </form>
          </div>
      </nav>
    <router-view/>
  </div>
</template>

<script>
import ComponentSearch from '@/components/ComponentSearch.vue'
import axios from 'axios';

  export default{
    components: {
      ComponentSearch
    },
    created(){
      this.getTags();
    },
    methods: {
       async getTags ()  {
        let url = process.env.VUE_APP_URL_API_TAGS;
        let resp = await axios.get(url)
        // eslint-disable-next-line no-console
        console.log('Este es env',url);
      }
    }
  }
</script>

<style>
/*#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}*/
</style>
