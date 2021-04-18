<template>
  <div class="content" v-if="result">
    <h1>{{ result.title }}</h1>
    <img :src="result.img" :alt="result.alt">
    <star-rating :border-width="4" border-color="#352c00" inactive-color="#bbb69c" active-color="#ffd91f" :rounded-corners="true" :star-points="[23,2, 14,17, 0,19, 10,34, 7,50, 23,43, 38,50, 36,34, 46,19, 31,17]" :show-rating="false" :star-size="40" :rating="rating" @rating-selected ="setRating"></star-rating>
  </div>
</template>

<script>
  import axios from "axios";
  import StarRating from 'vue-star-rating';

  export default {
    components: {
      StarRating
    },

    data: () => ({
      result: null,
      rating: 0
    }),

    methods:{
      async getComic(){
        axios.get("https://api.allorigins.win/raw?url=https://xkcd.com/info.0.json")
          .then((result) => {
            this.result = result.data;
          })
      },

      setRating(rating){
        localStorage.setItem('starts', rating);
        this.rating = parseInt(localStorage.getItem('starts'));
      }
    },

    created() {
      this.getComic();
      if (localStorage.starts) {
        this.rating = parseInt(localStorage.starts);
      }
    }
  }
</script>

<style lang="scss">
  @import "./scss/styles.scss";
</style>