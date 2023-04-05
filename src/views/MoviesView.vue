<script setup>
    import { ref, onMounted } from 'vue';

    let movies = ref([]);

    function fetchMovies(){
        fetch("/api/v1/movies", {
            method: 'GET',
        })
        .then(function (response) {
            return response.json();
        })
        .then(function (data) {
            // console.log(data);
            movies.value = data.data;
        })
        .catch(function (error) {
            console.log(error);
        });
    }

    onMounted(() => {
        fetchMovies();
    });
</script>

<template>

</template>