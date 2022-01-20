<template>
<main>
        <li>
            <img :src="imgLink" alt="">
            <h3>{{title}}</h3>
            <h3>{{originalTitle}}</h3>
            <h3><i :class="(originalLanguage == 'en') ? 'flag flag-us' : `flag flag-${ originalLanguage }`"></i></h3>
            <h3>vote: {{numTransform(vote)}}</h3>
            <div v-for="number in 5" 
            :key="number" 
            :class="(number <= numTransform(vote)) ? 'fas fa-star' : 'far fa-star'"></div>
        </li>
</main>
</template>

<script>
export default {
    name: 'Card',
    props: ['imgLink', 'title', 'originalTitle', 'originalLanguage', 'vote'],
    data() {
        return {
            
        }
    },
    methods: {
        numTransform(num) {
            let number = parseFloat(num);
            return Math.round(number / 2);
        }
    },
}
</script>

<style lang="scss">

</style>