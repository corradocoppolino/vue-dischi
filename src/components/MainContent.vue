<template>
  
    <main>

        <div class="row clearfix" v-if="!loading">

          <main-card 
          v-for="(element,index) in cards"
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

export default {
    name: 'MainContent',
    data(){
      return{
        cards: [],
        loading: true
      }
    },
    components: { 
      MainCard,
      Loader
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