<template>
    <div class="main-item">
        <h2>Titolo: {{ movieInfos.title }}</h2>
        <h3>Titolo Originale: {{ movieInfos.original_title }}</h3>
        <h5>Lingua: {{ movieInfos.original_language }}</h5>
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