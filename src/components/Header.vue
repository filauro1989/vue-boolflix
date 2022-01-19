<template>
    <div class="search">
        <input @keyup.enter="getApi" id="search" type="text" v-model="inputText" name="search">
        <button @click="getApi" class="btn btn-primary" type="submit">
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
            inputText:'',
            inputT:'',
            selectedMovies: [],
        }
    },
    methods: {
        getApi: function() {
            this.inputT = this.inputText.replace(/\s/g, "+");
            axios.get("https://api.themoviedb.org/3/search/movie?api_key=f134f75db1d5edf07240f2412a109c60&query=",
            {
                params: {
                    query: this.inputT
                }
            })
            .then((result) => {
                this.selectedMovies = result.data.results;
                this.$emit('doSearch', this.selectedMovies);
            })
            .catch((error) => {
                console.log(error);
            })
        }
    }
}
</script>

<style lang="scss">

</style>