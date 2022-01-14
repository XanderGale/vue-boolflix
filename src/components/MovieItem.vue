<template>
    <div class="main-item">
        <h2>Titolo: {{ movieInfos.title }}</h2>
        <h3>Titolo Originale: {{ movieInfos.original_title }}</h3>
        <h5>Lingua:</h5>
        <!-- Img se disponibile -->
        <span v-if="flags.includes(movieInfos.original_language)">
            <img :src="require('../assets/img/flags/' + movieInfos.original_language + '.png')" :alt="movieInfos.original_language + ' flag'">
        </span>
        <!-- Testo -->
        <span v-else>
            <h5>{{ movieInfos.original_language }}</h5>
        </span>
        
        <h4>Voto:</h4>

        <star-rating :rating="Math.round((movieInfos.vote_average / 2))" :read-only="true" :increment="0.01" :show-rating="false" :star-size="20" :inline="true"></star-rating>
    </div>
</template>

<script>
import StarRating from 'vue-star-rating';

export default {
    name: 'MovieItem',
    data: function(){
        return{
            flags: [
                'it',
                'en',
                'fr',
            ],
        };
    },
    components: {
        StarRating,
    },
    props: {
        movieInfos: Object,
    }
}
</script>

<style scoped lang="scss">

</style>