<template>
  <div id="app">
    
    <header-top />

    <main-content />

  </div>
</template>

<script>


import HeaderTop from './components/HeaderTop.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',
  components: {
    HeaderTop,
    MainContent
    
  },
  data(){
    return{
      axios
    }
  },
  
}
</script>

<style lang="scss">

@import '@/assets/style/general'

</style>
