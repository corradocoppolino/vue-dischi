<template>
  <div id="app">
    
    <header-top />

    <main-content />

  </div>
</template>

<script>

import "@fontsource/aclonica/index.css";
import HeaderTop from './components/HeaderTop.vue';
import MainContent from './components/MainContent.vue';

export default {
  name: 'App',

  components: {
    HeaderTop,
    MainContent  
  }

}
</script>

<style lang="scss">

@import '@/assets/style/general';

</style>
