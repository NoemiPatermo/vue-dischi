<template>
  <div id="app">
    <Header />
    <Main  :album="album"/> <!--invia al main i dati-->

  </div>
</template>

<script>
import axios from 'axios';  //importiamo axios
import Header from './components/Header.vue';
import Main from './components/Main.vue';

export default {
  name: 'App',
  components: {
    Header,
    Main         
  },
  data(){
    return{
      album: [] // oggetto che si popolerà solo quando avrai un dato dalla chiamata api
    }
  },
  created (){ //facciamo partire subito la chiamata 
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) =>{
      this.album = response.data.response
    })
  }
}
</script>

<style lang="scss">
 @import "./style/app.scss"
</style>
