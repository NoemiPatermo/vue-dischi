<template>
    <div class="loader">

        <span>Caricamento in corso...</span>
        
    </div>
</template>

<script>
export default {
    name: 'Loader'
}
</script>

<style lang="scss" scoped>
    .loader{
        position: fixed;
        left: 0;
        width: 100%;
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        background-color: #191919;
        span{
            color: white;
        }
    }
</style>