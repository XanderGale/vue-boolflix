<template>
    <div class="main-item">
        <h2>Titolo: {{ serieInfos.name }}</h2>
        <h3>Titolo Originale: {{ serieInfos.original_name }}</h3>
        <h5>Lingua:</h5>
        <!-- Img se disponibile -->
        <span v-if="flags.includes(serieInfos.original_language)">
            <img :src="require('../assets/img/flags/' + serieInfos.original_language + '.png')" :alt="serieInfos.original_language + ' flag'">
        </span>
        <!-- Testo -->
        <span v-else>
            <h5>{{ serieInfos.original_language }}</h5>
        </span>
        
        <h4>Voto:</h4>

        <star-rating :rating="Math.round((serieInfos.vote_average / 2))" :read-only="true" :increment="1" :show-rating="true" :star-size="20" :inline="true"></star-rating>
    </div>
</template>

<script>
import StarRating from 'vue-star-rating';

export default {
    name: 'SerieItem',
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
        serieInfos: Object,
    }
}
</script>

<style scoped lang="scss">

</style>