<template>
    <div class="album-container ">
        <div class="inner-album container">
        <img :src="poster" :alt=" 'poster of + ' + author" />
            <div class="title">{{title}}</div>  
            <div class="author">{{author}}</div>
            <div class="year">{{year}}</div>
        </div>
    </div>
</template>



<script>
export default {
    name: 'Album',
    props: { // qui passi la props del singolo album
        poster: String,
        title: String,
        author: String,
        year: String
    }
}
</script>


<style lang="scss" scoped>
    .album-container{
        text-align: center;
        margin-top: 10px;
        
        .inner-album {
            height: 300px;
            background: #2e3a46;
            padding: 20px;
            line-height: 20px;
                img{
                width: 100%;
            }
            .title{
                font-weight: bold;
                color: #fff;
                padding-top:10px;
            
            }
            .author{
                font-size: 15px;
                color: #808080;
            }
            .year{
                font-size: 12px;
                color: #808080;
            }
        }
        
    }

</style>