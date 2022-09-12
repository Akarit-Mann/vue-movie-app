<template>
  <div class="movie-detail">
    <h2>{{movie.Title}}</h2>
    <p>{{movie.Year}}</p>
    <img :src="movie.Poster" alt="pp" class="featured-img">
    <div class="p">{{movie.Plot}}</div>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { useRoute } from 'vue-router';
import { onBeforeMount } from '@vue/runtime-core';
import env from '@/env';
export default {
  setup() {
    const movie = ref({});
    const route = useRoute();

    onBeforeMount(()=>{
      fetch(`http://www.omdbapi.com/?apikey=${env.apikey}&i=${route.params.id}&plot=full`)
      .then(res => res.json())
      .then(data =>{
        movie.value = data
      })
    });

    return{
      movie,

    };
  }
}
</script>

<style lang="scss">
.movie-detail {
  padding: 16px;
  h2 {
    color: #FFF;
    font-size: 28px;
    font-weight: 600;
    margin-bottom: 16px;
  }
  .featured-img {
    display: block;
    max-width: 200px;
    margin-bottom: 16px;
  }
  p {
    color: #FFF;
    font-size: 18px;
    line-height: 1.4;
  }
}
</style>