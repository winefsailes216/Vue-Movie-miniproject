<template>
<div class="movie-detail">
    <img :src="movie.Poster" alt="" class="featured-img">
    <h2>{{movie.Title}}</h2>
    <p>{{movie.Year}}</p>
    <p>{{movie.Rating}}</p>
    
    <p>{{movie.Plot}}</p>
</div>
</template>

<script>
import {ref, onBeforeMount} from 'vue';
import {useRoute} from 'vue-router';
import env from '@/env.js';
 
export default {
    setup(){
        const movie = ref({});
        const route = useRoute();

        onBeforeMount(() => {
            fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
            .then(response => response.json())
            .then(data => {
                movie.value = data;
            });
        });

        return{
            movie
        }

    }
}
</script>

<style lang="scss">
.movie-detail{
    width: auto;
    height: auto;
    display: block;
    padding: 16px;
    text-align: center;

    h2{
        color: #fff;
        font-size: 28px;
        font-weight: 600;
        margin-bottom: 16px;
        
    }

    .featured-img{
        display: block;
        max-width: 200px;
        margin-bottom: 16px;
        
    }
    p{
        color: #fff;
        font-size: 18px;
        line-height: 1.4;
        
    }
    img{
        align-content: space-around;
        margin: auto;
        

    }
}
</style>