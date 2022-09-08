<template>
  <div id="app">
    <MainHeader  @selection="onSearch"/>
    <MainContent :search="searchProp" />
  </div>
</template>

<script>
  import MainHeader from './components/MainHeader.vue';
  import MainContent from './components/MainContent.vue';

  export default {
    name: 'App',
    components: {
      MainHeader,
      MainContent,
    },
    data(){
      return{
        searchProp: '',
      }
    },
    methods:{
      onSearch(data){
        this.searchProp = data
      }
    },
    
  }
</script>

<style lang="scss">

  #app {
    width: 100%;
    height: 100vh;
    background-color: #1E2D3B;
  }

</style>
