<template>
    <ul>
        <li>
            <h3>titolo</h3>
            <h3>titolo originale</h3>
            <h3>lingua</h3>
            <h3>voto</h3>
        </li>
    </ul>
</template>

<script>
import axios from 'axios';

export default {
    name: "Main",
    props: "completedApi",
    data() {
        return {
            selectedMovies: [],
        }
    },
    methods: {
        getMovies() {
            axios.get()
            .then()
            .catch()
        }
    },
}
</script>

<style lang="scss">

</style>