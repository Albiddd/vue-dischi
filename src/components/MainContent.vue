<template>
  <div class="container text-center">
    <div v-if="loading">
        <LoadingPage/>    
    </div>
    <div v-else class="card-wrapper">
      <CardComponent v-for="(disc, i) in filteredDiscs" :key="i" 
      :poster="disc.poster" 
      :album="disc.title"
      :author="disc.author" 
      :genre="disc.genre"
      :year="disc.year"/>

    </div>
  </div>
</template>

<script>
import CardComponent from './CardComponent.vue';
import axios from 'axios';
import LoadingPage from './LoadingPage.vue';

export default {
    name: "MainContent",
    components: { CardComponent, LoadingPage },
    props: {
      search:{
        type: String,
        default:'',
      }
    },
    data(){
      return{
        discs:[],
        loading: false,
      }
    },
    computed:{
      filteredDiscs(){
        const find = this.search.toLowerCase()
        if(find === 'all'){
          return this.discs
        } else{
          return this.discs.filter((el)=>{
            const genre = el.genre.toLowerCase()
            if(genre.includes(find)){
              return true
            }
            return false
          })
        }
      }
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

  @import '../styles/general.scss';

  .card-wrapper{
    display: grid;
    grid-template-columns: repeat(5, 1fr);
    gap: 40px;
    margin-top: 60px;
  }


</style>
