<template>

    <div class="loader"></div>
  
</template>
  
<script>

    export default {
        name: "LoadingPage",
    }
</script>
  
<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  
    @import '../styles/general.scss';
  
    .loader {
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%,-50%);
        border: 16px solid #fdfdfd;
        border-radius: 50%;
        border-top: 16px solid transparent;
        width: 120px;
        height: 120px;
        animation: spin 2s linear infinite;
    }

    @keyframes spin {
        0% { transform: rotate(0deg); }
        100% { transform: rotate(360deg); }
    }
  
</style>