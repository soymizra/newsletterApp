<template>
  <div id="app">
    <Navigation />
    <router-view/>
    <footer class="container-fluid bg-primary mt-5">
        <div class="container  p-3 text-white  rounded-top">
            <div class="row d-flex justify-content-center p-3">
                <ul class="footerNav">
                  <li class="nav-item active">
                    <a href="#" class="nav-link text-white">Privacy</a>
                  </li>
                  <li class="nav-item active">
                    <a href="#" class="nav-link text-white">FAQ</a>
                  </li>
                  <li class="nav-item active">
                    <a href="#" class="nav-link text-white">About us</a>
                  </li>
                  <li class="nav-item active">
                    <a href="#" class="nav-link text-white">Contact</a>
                  </li>
                </ul>
              
            </div>
            <div class="row d-flex justify-content-center p-3">
              Developed by    <a href="https://soymizra.github.io/portafolio/" target="_blank" class="text-white" style="text-decoration: underline; margin-left: .5rem">soymizra</a>
            </div>
        </div>
    </footer>
  </div>
</template>

<script>
import ComponentSearch from '@/components/ComponentSearch.vue'
import Navigation from '@/components/Navigation'
import axios from 'axios';

  export default{
    components: {
      ComponentSearch,
      Navigation
    },
    created(){
      this.getTags();
    },
    methods: {
       async getTags ()  {
        let url = process.env.VUE_APP_URL_API_TAGS;
        let resp = await axios.get(url)
        // eslint-disable-next-line no-console
        console.log('Este es res: ',resp);
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
.footerNav{
  display: flex;
  justify-content: space-between
}
.footerNav li{
  display: inline-block;
  vertical-align: top;
}
</style>
