<template>
    <div>
        <b-card
        :title="album"
        :img-src="poster"
        :img-alt="album"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="card p-4">
            <b-card-text class="card-text">
                <div>{{author}}</div>
                <div>{{year}}</div>
            </b-card-text>

        </b-card>
    </div>
  </template>
  
  <script>
  export default {
    name: 'CardComponent',
    props: {
        poster: String,
        album: {
            type: String,
            default: '../assets/kermit.png'
        },
        author: String,
        genre: String,
        year: String
    }
  }
  </script>
  
  <!-- Add "scoped" attribute to limit CSS to this component only -->
  <style scoped lang="scss">
  
    @import '../styles/variables.scss';

    .card{
        background-color: $light-bg;
        border-radius: 0px;
        height: 420px;
        color: white;
        .card-text{
            opacity: 0.3;
        }
    }
  
  </style>