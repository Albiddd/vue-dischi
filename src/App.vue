<template>
  <div id="app">
    <MainHeader/>
    <MainContent/>
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
    }
  }
</script>

<style lang="scss">

  #app {
    width: 100%;
    height: 100vh;
    background-color: #1E2D3B;
  }

</style>
