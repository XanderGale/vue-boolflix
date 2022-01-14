<template>
    <div class="main-item">
        <!-- Poster Image -->
        <div class="item-image">
            <img v-if="serieInfos.backdrop_path==null" src="../assets/img/404-img.png" alt="Image not available">
            <img v-else :src="'https://image.tmdb.org/t/p/w500' + serieInfos.backdrop_path" :alt="serieInfos.name + ' image'">
        </div>

        <div class="item-details">
            <h2>Titolo: {{ serieInfos.name }}</h2>
            <h3>Titolo Originale: {{ serieInfos.original_name }}</h3>
            <h5>Lingua:</h5>
            <!-- Img Lingua se disponibile -->
            <span v-if="flags.includes(serieInfos.original_language)">
                <img :src="require('../assets/img/flags/' + serieInfos.original_language + '.png')" :alt="serieInfos.original_language + ' flag'">
            </span>
            <!-- Testo -->
            <span v-else>
                <h5>{{ serieInfos.original_language }}</h5>
            </span>
            
            <h4>Voto:</h4>

            <star-rating :rating="Math.round((serieInfos.vote_average / 2))" :read-only="true" :show-rating="false" :star-size="20" :inline="true"></star-rating>
        </div>
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
    .main-item{
        display: flex;
        flex-flow: column nowrap;
        justify-content: flex-start;
        align-items: flex-start;

        min-width: 300px;
        max-width: 300px;

        min-height: 500px;
        max-height: 500px;

        margin: 0px 30px;

        background-color: green;
        .item-details{
            display: none;
        }
        .item-image{
            width: 100%;
            height: 100%;
            img{
                height: 100%;
                overflow: hidden;
                object-fit: cover;
                object-position: center;
            }
        } 
    }
</style>