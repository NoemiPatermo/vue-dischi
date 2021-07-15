<template>
  <div id="app">
    <Loader v-if="album.length == 0" /> <!--esisterà quando avrà tutti i dati-->
    <Header @choose="searchArtist"/>  <!--header lancia verso il padre il click (quando viene lanciato il choose, fai riferimento al metodo)-->
    <Main  :album="filteredArray"/> <!--invia al main i dati-->

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
      album: [],// oggetto che si popolerà solo quando avrai un dato dalla chiamata api
      filteredArray: [], 
                    
    }
  },
  created (){ //facciamo partire subito la chiamata 
    axios.get('https://flynn.boolean.careers/exercises/api/array/music').then((response) =>{
      this.album = response.data.response
      this.filteredArray = response.data.response
    })
  },
  methods: {  //il metodo lanciato, si aspetta argomento che viene inviato automaticamente
    searchArtist(searchMusic){ //filter per creare nuovo array
      this.filteredArray = this.album.filter((element) =>{
        return element.year.includes(searchMusic); // ricerca per anno 
      })
    }
  }
}
</script>

<style lang="scss">
 @import "./style/app.scss"
</style>
