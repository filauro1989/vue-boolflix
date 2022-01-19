<template>
    <div class="search">
        <input id="search" type="text" v-model="inputText" name="search">
        <button class="btn btn-primary" type="submit" @click="$emit('doSearch', inputText)">
            Cerca
        </button>
    </div>
</template>

<script>
export default {
    name: "Header",
    props: {
        inputValue: {
            type: String,
        }
    },
    data() {
        return {
            inputText:'',
        }
    },
}
</script>

<style lang="scss">

</style>