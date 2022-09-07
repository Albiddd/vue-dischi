<template>
    <header>
        <img src="../assets/logo.svg" alt="">
    </header>
  </template>
  
  <script>
  export default {
    name: 'MainHeader',
    props: {
  
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">

    @import '../styles/variables.scss';

    header{
        background-color: $light-bg;
        img{
            padding: 20px;
            width: 200px;
        }
    }
  
  </style>