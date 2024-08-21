<script>
import axios from 'axios';

export default{
    data() {
        return{
            projects: [],
        }
    },
    methods: {
        getProjects() {
            axios.get('http://127.0.0.1:8000/api/projects/', {
                params: {
                    
                }
            })
                .then((response) => {
                    console.log(response.data.results.data);
                    this.projects = response.data.results.data;
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
    }
}
</script>

<template>
  <h1>Content</h1>

  <ul>
    <li v-for="project in projects">
      {{ project.title }}
    </li>
  </ul>
</template>

<style lang="scss" scoped>

</style>