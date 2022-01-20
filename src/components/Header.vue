<template>
    <div class="search">
        <input @keyup.enter="getMerged" id="search" type="text" v-model="inputText" name="search">
        <button @click="getMerged" class="btn btn-primary" type="submit">
            Cerca
        </button>
    </div>
</template>

<script>
import axios from 'axios'
export default {
    name: "Header",
    data() {
        return {
            query: 'https://api.themoviedb.org/3/search/',
            api_key: 'f134f75db1d5edf07240f2412a109c60',
            language: 'en-US',
            inputText:'',
            // inputT:'',
            selectedMerged: {
                selectedMovies: [],
                selectedTv: [],
            },
        }
    },
    methods: {
        getFilms: function() {
            const endpoint = 'movie';
            const parameters = {
                api_key: this.api_key,
                language: this.language,
                query: this.inputText,
            }
            // this.inputT = this.inputText.replace(/\s/g, "+");
            axios.get(`${this.query}${endpoint}`, { params: parameters })
            .then((result) => {
                this.selectedMerged.selectedMovies = result.data.results;
                // this.$emit('doSearch', this.selectedMovies);
            })
            .catch((error) => {
                console.log(error);
            })
        },
        getTv: function() {
            const endpoint = 'tv';
            const parameters = {
                api_key: this.api_key,
                language: this.language,
                query: this.inputText,
            }
            axios.get(`${this.query}${endpoint}`, { params: parameters })
            .then((result) => {
                this.selectedMerged.selectedTv = result.data.results;
                // this.$emit('doSearch', this.selectedMovies);
            })
            .catch((error) => {
                console.log(error);
            })
        },
        getMerged: function() {
            this.getFilms();
            this.getTv();
            setTimeout(() => {
                this.$emit('doSearch', this.selectedMerged)          
                
            }, 500);
        }
    }
}
</script>

<style lang="scss">

</style>