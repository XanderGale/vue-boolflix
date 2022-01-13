<template>
    <main>
        <MovieItem v-for='(movie, index) in moviesList' :key="index" :movieInfos="movie"/>
    </main>
</template>

<script>
import MovieItem from "./MovieItem.vue";

export default {
    name: 'Main',
    components: {
        MovieItem,
    },
    props: {
        moviesList: Array,
    }
}
</script>

<style scoped lang="scss">

</style>