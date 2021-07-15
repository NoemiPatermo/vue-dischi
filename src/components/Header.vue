<template>
    <div class="header-container ">
        <div class="spotify-logo">
            <img src="../assets/spotify-logo.png" alt="logo-spotify">
        </div>
        
        <div class="box-container">
            <input type="text" placeholder="  choose"
             v-model="searchMusic"
             @keyup.enter="$emit('choose', searchMusic)"/> <!--viene lanciato l'evento verso il padre con il dato pure (searchmusic)-->
            <button>Choose</button>
        </div>
                
        
        
    </div>
</template>

<script>
export default {
    name: 'Header',
    data (){
        return{
            searchMusic: ''
        }
    }
}
</script>

<style lang="scss" scoped>
    .header-container{
        display: flex;
        justify-content: space-between;
        text-align: center;
        background-color: #2e3a46; 
        padding: 20px;
        img{
            width: 70px;
            
        }
        .box-container{
           
            width: 50%;
            input{
                width: 50%;
                margin-right: 20px;
            }
            
        }
    }
 

</style>