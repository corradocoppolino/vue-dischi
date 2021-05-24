<template>
  
    <main>

        <div class="row clearfix">

          <main-card 
          v-for="(element,index) in cards"
          :key="index"
          :carta="element"
          />

        </div>

    </main>

</template>

<script>

import MainCard from './MainCard.vue'
import axios from 'axios';

export default {
    name: 'MainContent',
    data(){
      return{
        cards: []
      }
    },
    components: { 
      MainCard,
    },
    created(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then(res => {
        console.log(res.data);
        this.cards = res.data.response;
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
    .row{
      width: 80%;
      margin: auto;
    }
}

</style>