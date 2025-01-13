<script setup>
import { reactive } from "vue";
import { items } from "./movies.json";
 let movies = reactive(items);
/*
 This is an Icon that you can use to represent the stars if you like
 otherwise you could just use a simple ⭐️ emoji, or * character.
*/
// import { StarIcon } from "@heroicons/vue/24/solid";

function rateMovie(movieIndex, index)
{
  movies[movieIndex].rating = index;
}
</script>

<template>

  <div>
    <div class="film" v-for="(item, movieIndex) in movies" :key="movieIndex">
      <div>
        <img :src="item.image" />
        <span style="margin: 5px;"> {{ item.name }}</span>
        <div></div>
        <div class="genre" v-for="genre in item.genres">
          <div>{{ genre }}</div>
        </div>
        <div style="word-wrap: break-word; width:350px; margin: 5px;">{{ item.description }}</div>
        <div class="rating">Rating ({{ item.rating }}/5)
          <div class="stars" v-for="index in 5">
            <button :class="{'starColor': index <= item.rating}"  @click="rateMovie(movieIndex, index)">★</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

