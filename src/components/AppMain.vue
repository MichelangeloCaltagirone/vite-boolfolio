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
            axios.get('/user?ID=12345')
                .then(function (response) {
                    // handle success
                    console.log(response);
                })
                .catch(function (error) {
                    // handle error
                    console.log(error);
                })
            }
        }
}

</script>

<template>

    <main>
        <div class="container">

        </div>
    </main>

</template>

<style>
</style>