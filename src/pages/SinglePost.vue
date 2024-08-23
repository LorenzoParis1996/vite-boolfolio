<script>
import axios from 'axios';

import SingleCard from '../components/SingleCard.vue';
export default{
    data() {
        return{
            project: {},
            
            
            
        }
    },
    methods: {
        getProjects(id) {
            axios.get(`http://127.0.0.1:8000/api/projects/${id}`, {
                params: {
                     
                }
            })
                .then((response) => {
                    console.log(response.data.results);
                    this.project = response.data.results;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });
        }
    },
    created(){
        this.getProjects(this.$route.params.id);
    },
    components:{
        SingleCard
    } 
}
</script>

<template>
   
   <SingleCard :title="project.title" :developer="project.developer" :type="project.type.name" :technologies="project.technologies" :release_date="project.release_date" :description="project.description"/>

</template>

<style lang="scss" scoped>

</style>