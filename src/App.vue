<script setup>
import { items } from "./movies.json";
/*
 This is an Icon that you can use to represent the stars if you like
 otherwise you could just use a simple ⭐️ emoji, or * character.
*/
// import { StarIcon } from "@heroicons/vue/24/solid";
</script>

<template>

  <div>
    <div class="film" v-for="item in items">
      <div>
        <img :src="item.image" />
        <span style="margin: 5px;"> {{ item.name }}</span>
        <div></div>
        <div class="genre" v-for="genre in item.genres">
          <div>{{ genre }}</div>
        </div>
        <div style="word-wrap: break-word; width:350px; margin: 5px;">{{ item.description }}</div>
        <div class="rating">Rating ({{ item.rating }}/5)
          <div class="stars" v-for="index in item.rating">
            <span>★</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
.film {
  display: inline-block;
  vertical-align: bottom;
  margin: 10px 10px 10px 10px;
  background-color: white;
  width: 350px;
  height: 650px;
}

.genre {
  display: inline-block;
  margin: 5px 5px 5px 5px;
  background-color: blueviolet;
  color: white;
  border-radius: 8px;
}

.rating {
  position: absolute;
  top: 620px;
  margin: 10px;
}

.stars {
  display: inline-block;
  color: yellowgreen;
}

img {
  width: 350px;
  height: 400px !important;
}
</style>
