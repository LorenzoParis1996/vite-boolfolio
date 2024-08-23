<script>
import axios from 'axios';

export default{
    data() {
        return{
            
            
            
            
        }

    },
    
    props:{
        title:{
            typeof: String,
            required:true
        },
        developer:{
            typeof: String,
            required:true
        },
        type:{
            typeof: String,
            required:true
        },
        technologies:{
            typeof: Array,
            required:true
        },
        release_date:{
            typeof: String,
            required:true
        },
        description:{
            typeof: String,
            required:true
        },
    }
}    
</script>

<template>
  <div class="card mb-3" style="width: 30rem;">
  <div class="card-body">
    <h5 class="card-title">{{ title }}</h5>
    <h6 class="card-subtitle mb-2 text-muted">{{ developer }}</h6>
    <p class="card-text">{{ type }}</p>     
    <p class="card-text" v-for="technology in technologies">{{ technology.name }}</p>
         
    <p class="card-text">{{ release_date }}</p>       
    <p class="card-text">{{ description }}</p>
  </div>
</div>


</template>

<style lang="scss" scoped>

</style>