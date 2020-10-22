<template>
 <div class="emoji">
   <img id="imgGif">
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
    
    const callEmoji = async () => {
     const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
     const { data: gifs } = await gf.emoji();
     const random = Math.floor(Math.random() * 26);
     const gif = gifs[random].images.downsized.url
     const image = document.getElementById('imgGif');
     image.setAttribute('src', gif);
   }

    callEmoji()
  }
}
</script>