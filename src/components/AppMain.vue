<script>
import axios from 'axios';

export default {
    name: "AppMain",
    data() {
        return {
            projectList: [],
        }
    },
    methods: {
        getProjects(){
            axios.get('http://127.0.0.1:8000/api/projects')
                .then((response) => {
                    // handle success
                    console.log(response.data.result);
                    this.projectList = response.data.result;
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
            }
    },
    created(){
        this.getProjects();
    }
}

</script>

<template>

    <main>

        <div class="container">
            <h1>Projects List</h1>

            <div class="my-1" v-for="project in projectList" :key="project.id">
                <div class="card">
                    <div class="card-body">
                        <h3 class="card-title"><strong>Project Name:</strong> {{ project.name }}</h3>
                        <h5 class="card-subtitle"><strong>Project Author:</strong> {{ project.author }}</h5>
                        <p class="card-text mt-1"><strong>Description</strong><br> {{ project.description }}</p>
                    </div>
                </div>
            </div>
        </div>

    </main>

</template>

<style>
</style>