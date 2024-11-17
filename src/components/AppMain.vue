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
                .then(function (response) {
                    // handle success
                    console.log(response);
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
            <h1>Ciao, Funziono</h1>
        </div>
    </main>

</template>

<style>
</style>