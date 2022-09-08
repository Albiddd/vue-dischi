<template>
    <header>
        <img src="../assets/logo.svg" alt="">
        <div class="filter-genre">
          <!-- <input v-model="search" @keyup.enter="$emit('search', search)" type="text" class="rounded"> -->
          
          <select name="genre" id="genre" v-model="selected" @change="$emit('selection', selected)">
            <option value="all">All</option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Metal">Metal</option>
            <option value="Jazz">Jazz</option>
          </select> 

        </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'MainHeader',
    props: {
      genreList: Array
    },
    data(){
      return{
        selected:'all'
      }
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">

    @import '../styles/variables.scss';

    header{
        background-color: $light-bg;
        display: flex;
        justify-content: space-between;
        align-items: center;
        img{
            padding: 20px;
            width: 200px;
        }
        .filter-genre{
          padding: 0 20px;
        }
    }
  
  </style>