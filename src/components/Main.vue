<template>
    <main>

        <h2>Movies</h2>
        <div class="movies list">
            <MovieItem v-for='(movie) in moviesList' :key="movie.id" :movieInfos="movie"/>
        </div>
        
        <h2>Tv Shows</h2>
        <div class="series list">
            <SerieItem v-for='(serie) in seriesList' :key="serie.id" :serieInfos="serie"/>
        </div>
        
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
    main{
        height: calc(100vh - 70px);
        overflow-y: auto;
        padding: 10px;
        color: white;

        background: rgb(0,0,0);
        background: linear-gradient(180deg, rgba(61,61,61,1) 0%, rgba(0,0,0,1) 84%);
        h2{
            font-size: 30px;
        }
        .list{
            padding: 40px 0;

            display: flex;
            flex-flow: row nowrap;
            justify-content: flex-start;
            align-items: center;

            overflow-x: auto;
        }
    }
</style>