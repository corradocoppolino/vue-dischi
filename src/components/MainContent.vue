<template>
  
    <main>

        <div class="row clearfix" v-if="!loading">


          <main-filter 
          @searchGen="searchingGen"
          @searchAlb="searchingAlb"
          />

          <main-card 
          v-for="(element,index) in filteredCard"
          :key="index"
          :carta="element"
          />

        </div>

        <loader v-else />

    </main>

</template>

<script>

import MainCard from './MainCard.vue'
import axios from 'axios';
import Loader from './Loader.vue';
import MainFilter from './MainFilter.vue';

export default {
    name: 'MainContent',
    data(){
      return{
        cards: [],
        loading: true,
        textGen: "",
        textAlb: ""
        
      }
    },
    components: { 
      MainCard,
      Loader,
      MainFilter
    },
  
    created(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then(res => {
        console.log(res.data);
        this.cards = res.data.response;
        this.loading = false;
      })
      .catch(err => {
        console.log(err);
    })
      
    },

    computed:{

      filteredCard(){

        if(this.textGen === "" && this.textAlb === ""){
          return this.cards.filter(elemento => elemento.genre !== undefined)
        }else if(this.textGen !== "" && this.textAlb === ""){
          return this.cards.filter(elemento => elemento.genre.toLowerCase().includes(this.textGen.toLowerCase()))
        }else{
          return this.cards.filter(elemento => elemento.author.toLowerCase().includes(this.textAlb.toLowerCase()))
        } 
        
      }
    },

    methods:{
      searchingGen(text){
        this.textGen = text;
      },

      searchingAlb(text){
        this.textAlb = text;
      }
    }

}
</script>

<style lang="scss" scoped>

main{
    background-color: #1E2D3B;
    min-height: 1024px;
    .row{
      width: 80%;
      margin: auto;
    }
}

</style>