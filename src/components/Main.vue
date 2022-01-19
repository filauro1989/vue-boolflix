<template>

</template>

<script>
export default {
    name: "Main",
    data() {
        return {
            queryPath: 'https://api.themoviedb.org/3/search/movie?api_key=f134f75db1d5edf07240f2412a109c60',
            movies: [],
        }
    },
    methods: {
        getMovies() {
            axios.get(this.queryPath)
            .then((result) => {
                this.movies = 
            })
            .catch()
        }
    },
}
</script>

<style lang="scss">

</style>