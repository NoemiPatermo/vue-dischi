<template>
    <div class="header-container ">
        <div class="spotify-logo">
            <img src="../assets/spotify-logo.png" alt="logo-spotify">
        </div>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
    .header-container{
        height: 90px;
        background-color: #2e3a46; 
        img{
            width: 70px;
            margin: 10px;
        }
    }

</style>