<template>
  <div id="app">
    
    <header class="text-center mt-4">
      <h3 class="text-center">Rick and Morty app</h3>
    </header>

    <search-bar @search="filterResults" @reset="resetFilter" />
    <main-container  :personaggi="personaggiFiltered" />
    
  </div>
</template>

<script>
import MainContainer from './components/MainContainer.vue';
import SearchBar from './components/SearchBar.vue';
import axios from 'axios';



export default {
  name: 'App',
  components: {
    MainContainer,
    SearchBar,
  },
  data(){
    return {
      personaggi: [],
      personaggiFiltered: []
    }
  },
  mounted(){
    axios.get('https://api.sampleapis.com/rickandmorty/characters').then((response) => {
      this.personaggi = response.data
      this.personaggiFiltered = response.data
    })
  },
  methods: {
    filterResults (keyword){
      this.personaggiFiltered = this.personaggi.filter((personaggio) => {
      return personaggio.name.toLowerCase().includes(keyword)
      });
    },
    resetFilter(){
     this.personaggiFiltered = this.personaggi;
    }
  }

}
</script>

<style lang="scss">
@import './style/main.scss'
</style>
