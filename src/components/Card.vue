<template>
<main>
        <li>
            <img :src="imgLink" alt="">
            <h3>{{title}}</h3>
            <h3>{{originalTitle}}</h3>
            <h3><i :class="(originalLanguage == 'en') ? 'flag flag-us' : `flag flag-${ originalLanguage }`"></i></h3>
            <h3>{{vote}}</h3>
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
}
</script>

<style lang="scss">

</style>