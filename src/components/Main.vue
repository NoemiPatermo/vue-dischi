<template>

  <div class="layout-container">
      <div class="container">
        <div class="row">
        <!--qui hai il v-for -->
            <Album class="album-section" v-for="album in album" :key='album.index'
            :poster='album.poster'
            :title='album.title'
            :author='album.author'
            :year='album.year'/>
        </div>
      </div>
    </div>
</template>

<script>

import Album from './Album.vue'; //importi sul main, il tuo component

export default {
    name: 'Main',

    components:{
        Album    //lo richiami, dichiari il tuo component
    },
    props: {
        album: Array
    }
}
</script>

<style lang="scss" scoped>
    .layout-container {
        background-color:#1e2d3b ;
        padding: 40px;
        .row{
            .album-section{
            width: calc(100% /5);
            padding: 20px;
            
            }
        }
    }
    
</style>