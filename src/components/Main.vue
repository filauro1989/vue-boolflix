<template>
    <ul>
        <li v-for="(movie, index) in Movies" :key="index">
            <h3>{{movie.title}}</h3>
            <h3>{{movie.original_title}}</h3>
            <h3><i :class="(movie.original_language == 'en') ? 'flag flag-us' : `flag flag-${ movie.original_language }`"></i></h3>
            <h3>{{movie.vote_average}}</h3>
        </li>
    </ul>
</template>

<script>

export default {
    name: "Main",
    props: ['Movies'],
    data() {
        return {

        }
    },
}
</script>

<style lang="scss">

</style>