<template>
  <div id="app">
    <Loader v-if="album.length == 0" /> <!--esisterà quando avrà tutti i dati-->
    <Header />
    <Main  :album="album"/> <!--invia al main i dati-->

  </div>
</template>

<script>
import axios from 'axios';  //importiamo axios
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Loader from './components/Loader.vue';
export default {
  name: 'App',
  components: {
    Header,
    Main,
    Loader        
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
