<template>
    <div class="main-item">
        <h2>Titolo: {{ movieInfos.title }}</h2>
        <h3>Titolo Originale: {{ movieInfos.original_title }}</h3>
        <h5>Lingua:</h5> <img :src="require('../assets/img/flags/' + movieInfos.original_language + '.png')" :alt="movieInfo.original_language">
        <h4>Voto: {{ movieInfos.vote_average }}</h4>
    </div>
</template>

<script>
export default {
    name: 'MovieItem',
    props: {
        movieInfos: Object,
    }
}
</script>

<style scoped lang="scss">

</style>