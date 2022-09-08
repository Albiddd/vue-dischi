<template>
  <div id="app">
    <MainHeader :artistsList="getArtists" :genreList="getGenres" @selectionArtist="onSearch" @selectionGenre="onSearch"/>
    <MainContent :loading="loading" :discs="discs" :search="searchProp" />
  </div>
</template>

<script>
  import MainHeader from './components/MainHeader.vue';
  import MainContent from './components/MainContent.vue';
  import axios from 'axios';

  export default {
    name: 'App',
    components: {
      MainHeader,
      MainContent,
    },
    data(){
      return{
        discs:[],
        loading: false,
        searchProp: '',
      }
    },
    methods:{
      onSearch(data){
        this.searchProp = data
      }
    },
    computed: {
        getGenres() {
            const genreList = [];
            this.discs.forEach ((disc) => {
                if (!genreList.includes(disc.genre)) {
                    genreList.push(disc.genre);
                }
            });            
            console.log(genreList)
            return genreList;
        },
        getArtists() {
            const artistsList = [];
            this.discs.forEach ((disc) => {
                if (!artistsList.includes(disc.author)) {
                    artistsList.push(disc.author);
                }
            });
            console.log(artistsList)
            return artistsList;
        },
    },
    created(){
      this.loading = true;
      axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((res)=> {
          console.log(res.data.response);
          this.discs = res.data.response;
        })
        .catch(()=> {

        })
        .finally(()=>(this.loading = false))
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
