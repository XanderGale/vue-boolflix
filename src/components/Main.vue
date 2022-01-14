<template>
    <main>
        <h2>Movies:</h2>
        <MovieItem v-for='(movie) in moviesList' :key="movie.id" :movieInfos="movie"/>
        <h2>Tv Shows:</h2>
        <SerieItem v-for='(serie) in seriesList' :key="serie.id" :serieInfos="serie"/>
    </main>
</template>

<script>
import MovieItem from "./MovieItem.vue";
import SerieItem from "./SerieItem.vue";

export default {
    name: 'Main',
    components: {
        MovieItem,
        SerieItem,
    },
    props: {
        moviesList: Array,
        seriesList: Array,
    }
}
</script>

<style scoped lang="scss">

</style>