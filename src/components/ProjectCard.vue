<script>
import axios from 'axios';
import SingleCard from './SingleCard.vue';

export default{
    data() {
        return{
            projects: [],
            //currentPage: 1,
            
            
        }
    },
    methods: {
        getProjects(page = 1) {
            axios.get('http://127.0.0.1:8000/api/projects/', {
                params: {
                    page:page 
                }
            })
                .then((response) => {
                    console.log(response.data.results.data);
                    this.projects = response.data.results.data;
                    //this.projects.push(...response.data.results.data);
                    //this.currentPage = response.data.results.page;
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
        this.getProjects();
    },
    components:{
        SingleCard
    }
}
</script>

<template>
<ul>
    <router-link v-for="project in projects" :to="{name: 'single-project', params: {id: project.id}}" class="text-decoration-none">

        <SingleCard :title="project.title" :developer="project.developer" :type="project.type.name" :technologies="project.technologies" :release_date="project.release_date" :description="project.description"/>
    </router-link>
</ul>


<!--<div class="card mb-3" style="width: 30rem;" v-for="project in projects">
  <div class="card-body">
    <h5 class="card-title">{{ project.title }}</h5>
    <h6 class="card-subtitle mb-2 text-muted">{{ project.developer }}</h6>
    
    <p class="card-text">{{ project.technologies.name }}</p>
         
    <p class="card-text">{{ project.type.name }}</p>     
    <p class="card-text">{{ project.release_date }}</p>       
    <p class="card-text">{{ project.description }}</p>
  </div>
</div>

<div>
    <button class="btn btn-primary btn-lg" @click.prevent="getProjects(currentPage + 1)">Show more</button>
</div>-->
</template>

<style lang="scss" scoped>

</style>