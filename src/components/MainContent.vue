<template>
  
    <main>

        <main-card 
        v-for="(element,index) in cards"
        :key="index"
        />

    </main>

</template>

<script>

import MainCard from './MainCard.vue'
import axios from 'axios';

export default {
    components: { 
      MainCard,
      cards: [] 
    },
    created(){
    axios.get("https://flynn.boolean.careers/exercises/api/array/music")
      .then(res => {
        console.log(res.data);
        this.cards = res.data;
      })
      .catch(err => {
        console.log(err);
      })
  }


}
</script>

<style lang="scss" scoped>

main{
    height: 500px;
    background-color: #1E2D3B;
}

</style>