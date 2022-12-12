<template>
  <div class="home">
    <Hero />
  </div>
</template>

<script>
// import axios from 'axios'
import { axios } from 'axios';
// const axios = require('axios')

export default {
  name: 'IndexPage',
  data() {
    return {
      movies: []
    }
  },
  async fetch() {
    await this.getMovies()
  },
  methods: {
    async getMovies() {
      const data = axios.get(
        'https://api.themoviedb.org/3/movie/now_playing?api_key=7e44f0e9c2f9e13181ca05a830e626fd&language=en-US&page=1'
      )

      const result = await data
      console.log('result ', result);
    }
  },
}
</script>
