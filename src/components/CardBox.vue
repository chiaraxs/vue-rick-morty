<template>
    
    
        <div class="characters">
            
            <img :src="personaggio.image">
            <h4>{{personaggio.name}}</h4>
            <h6>{{personaggio.origin}}</h6>
            <h6 class="fw-bolder">{{personaggio.species}}</h6>
        </div>
    
</template>


<script>
export default {
    props: {
       personaggio: Object
    },
}
</script>


<style lang="scss" scoped>

    
    .characters {
        width: 20%;
        text-align: center;
        margin: 50px 5px 20px 5px;

        img{
            width: 200px;
            border-radius: 50%;
        }

        h6{
            font-weight: lighter;
        }

            
    }
        
        
    
</style>