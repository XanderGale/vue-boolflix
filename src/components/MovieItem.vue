<template>
    <div class="main-item">
        <!-- Poster Image -->
        <div class="item-image">
            <img v-if="movieInfos.backdrop_path==null" src="../assets/img/404-img.png" alt="Image not available">
            <img v-else :src="'https://image.tmdb.org/t/p/w342' + movieInfos.backdrop_path" :alt="movieInfos.name + ' image'">
        </div>

        <div class="item-details">
        
            <ul>
                <!-- Titolo -->
                <li>
                    <h2>Titolo: {{ movieInfos.title }}</h2>
                </li>
                <!-- Titolo Originale -->
                <li>
                    <h3>Titolo Originale: {{ movieInfos.original_title }}</h3>
                </li>
                <!-- Lingua -->
                <li>
                    <h5>Lingua:</h5>
                    <!-- Img Lingua se disponibile -->
                    <span v-if="flags.includes(movieInfos.original_language)">
                        <img :src="require('../assets/img/flags/' + movieInfos.original_language + '.png')" :alt="movieInfos.original_language + ' flag'">
                    </span>
                    <!-- Testo se immagine lingua non disponibile -->
                    <span v-else>
                        <h5>{{ movieInfos.original_language }}</h5>
                    </span>
                </li>
                <!-- Rating -->
                <li>
                    <h4>Voto:</h4>

                    <star-rating :rating="Math.round((movieInfos.vote_average / 2))" :read-only="true" :show-rating="false" :star-size="20" :inline="true"></star-rating>

                </li>
            </ul>
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
        movieInfos: Object,
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

        width: 300px;
        height: 500px;

        min-height: 500px;
        max-height: 500px;

        margin: 0px 30px;

        overflow: hidden;

        background: rgb(0,0,0);
        background: linear-gradient(180deg, rgba(61,61,61,1) 0%, rgba(0,0,0,1) 84%);

        -webkit-box-shadow: 5px 5px 15px 5px rgba(61,61,61,1); 
        box-shadow: 5px 5px 15px 5px rgba(61,61,61,1);
        .item-details{
            display: none;
            padding: 10px;
        }
        ul{
            list-style-type: none;
            height: 100%;
            width: 100%;
        }
        .item-image{
            width: 100%;
            height: 100%;
            img{
                height: 100%;
                width: 100%;
            }
        }
    }
    .main-item:hover .item-details{
        display: block;
    }
    .main-item:hover .item-image{
        display: none;
    }
</style>