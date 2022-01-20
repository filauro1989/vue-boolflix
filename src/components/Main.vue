<template>
    <!-- <main>
        <ul v-if="Movies.films.length > 0">
            <li v-for="(movie, index) in Movies.films" :key="index+'film'">
                <img :src="baseLink + movie.poster_path" alt="">
                <h3>{{movie.title}}</h3>
                <h3>{{movie.original_title}}</h3>
                <h3><i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h3>
                <h3>{{movie.vote_average}}</h3>
            </li>
        </ul>
        <h1 v-else> Nessun Film Trovato </h1>
        <ul v-if="Movies.series.length > 0">
            <li v-for="(movie, index) in Movies.series" :key="index+'series'">
                <img :src="baseLink + movie.poster_path" alt="">
                <h3>{{movie.name}}</h3>
                <h3>{{movie.original_name}}</h3>
                <h3><i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h3>
                <h3>{{movie.vote_average}}</h3>
            </li>
        </ul>
            <h1 v-else> Nessuna Serie Trovata </h1>
    </main> -->
    <main>
        <ul v-if="Movies.films.length > 0">
            <Card v-for="(movie, index) in Movies.films" :key="index + 'film'" :imgLink="baseLink + movie.poster_path" :title="movie.title" :originalTitle="movie.original_title" :originalLanguage="movie.original_language" :vote="movie.vote_average" />
        </ul>
        <ul v-if="Movies.films.length > 0">
            <Card v-for="(movie, index) in Movies.series" :key="index + 'series'" :imgLink="baseLink + movie.poster_path" :title="movie.title" :originalTitle="movie.original_title" :originalLanguage="movie.original_language" :vote="movie.vote_average" />
        </ul>
    </main>


</template>

<script>
import Card from "./Card.vue";

export default {
    name: "Main",
    props: ['Movies', 'baseLink'],
    components: {
        Card,
    },
    data() {
        return {

        }
    },
}
</script>

<style lang="scss">

</style>