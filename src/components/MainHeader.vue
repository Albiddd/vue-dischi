<template>
    <header>
        <img src="../assets/logo.svg" alt="">
        <div class="filters">
          <!-- <input v-model="search" @keyup.enter="$emit('search', search)" type="text" class="rounded"> -->
          
          <select name="genre" id="genre" v-model="selected" @change="$emit('selectionGenre', selected)">
            <option value="all">All Genre</option>
            <option v-for="(genre, index) in genreList" :key="index" 
            :value="genre">
              {{genre}}
            </option> 
          </select> 

          <select name="author" id="author" v-model="selected" @change="$emit('selectionArtist', selected)">
            <option value="all">All Artists</option>
            <option v-for="(author, index) in artistsList" :key="index" 
            :value="author">
              {{author}}
            </option> 
          </select> 


        </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'MainHeader',
    props: {
      genreList: Array,
      artistsList: Array
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
        .filters{
          padding: 0 20px;
          select{
            margin: 0 10px;
          }
        }
    }
  
  </style>