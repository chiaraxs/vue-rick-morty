<template>
    
    <div class="input-zone d-flex justify-content-center mt-3">
      <input type="text" placeholder="Search Character" class=" mt-2 p-2 w-50" v-model="keywordSearch" @keyup.enter="$emit('search', keywordSearch)">
      <button @click="$emit('search', keywordSearch)" type="button" class="btn btn-primary ms-2">Search</button>
      <button @click="resetAll" type="button" class="btn btn-warning ms-2">Reset</button>
    </div>

</template>



<script>
export default {
    data() {
        return {
            keywordSearch: '',
        }
    },
    methods: {
        resetAll(){
            this.keywordSearch = '';    // svuoto l'input al resetAll
            this.$emit('reset');        // richiamo l'emit reset
        }
            

    }
}
</script>


<style lang="scss" scoped>

</style>