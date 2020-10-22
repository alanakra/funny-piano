<template>
 <div class="emoji">
   <img id="imgGif" :src="src" v-if="src"/>
 </div>
</template>

<style scoped>
 .emoji{
  height: 200px;
  width: 200px;
  }
</style>

<script>
  import { GiphyFetch } from '@giphy/js-fetch-api'

  export default {
   mounted(){
  },

  data(){
    return {
      src: null
    }
  },

  methods: {
     async callEmoji () {
     const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
     const { data: gifs } = await gf.emoji();
     const random = Math.floor(Math.random() * 24);
     const gif = gifs[random].images.downsized.url

    this.src = gif
   }

  }
    
  
}
</script>