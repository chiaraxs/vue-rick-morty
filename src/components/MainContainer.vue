<template>


  <div class="container ">
    
    <div class="main d-flex justify-content-center flex-wrap">
      
      <card-box v-for="personaggio in personaggi" 
      :key="personaggio.id" 
      :personaggio="personaggio"
      class="card-box" />
      
  </div>
  </div>
  
    
</template>


<script>
import CardBox from './CardBox.vue'

export default {
  components: {
    CardBox,
    },
  props: {
    personaggi: Array
    },
    
}
</script>


<style lang="scss" scoped>

main {
  width: 1200px;
}


</style>