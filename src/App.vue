<template>
  <div id="app">
    <TheHeader />
    
    <MusicList />

  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import MusicList from './components/MusicList.vue';

export default {
  name: 'App',
  components: { TheHeader, MusicList }
};
</script>

<style lang="scss">
@import "./assets/scss/general";
</style>
