<template>
  <div class="cardContainer">
    <div
      class="card"
      style="width: 22rem"
      v-for="(show, index) in tvShowsArray"
      :key="index"
      
    >
      <img
        :src="imageURL + show.poster_path"
        class="card-img-top"
        alt="..."
      />
      <div class="card-body">
        <h4 class="card-title">{{show.name}}</h4>
        <p class="card-text">{{show.overview}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "vueCard",
  props: {},
  data() {
    return {
      numberOfTvShows: 4,
      tvShowsArray: [{ name: "random show" }],
      imageURL: "https://image.tmdb.org/t/p/w342",
    };
  },
  async mounted() {
    let result = await axios.get(
      "https://api.themoviedb.org/3/tv/popular?api_key=1b62ccff88d2cd537027e1d82920197b&language=en-US&page=1%22"
    );
    var tvShowsResult = result.data.results;
    var i = 0;
    for (i = 0; i < this.numberOfTvShows; i++) {
      console.log(tvShowsResult[i]);
      this.tvShowsArray[i] = tvShowsResult[i];
    }
    
  },
};
</script>
