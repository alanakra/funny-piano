<template>
 <div class="emoji">
  
 </div>
</template>

<style scoped>
 .emoji{
  height: 200px;
  width: 200px;
  background-color: royalblue;
  }
</style>

<script>
  import { GiphyFetch } from '@giphy/js-fetch-api'
export default {
  mounted(){
    
    const callEmoji = async () => {
     const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
     const { data: gifs } = await gf.emoji({ limit: 1 })
     const image = gifs[0].embed_url
     console.log(image)
   }

    callEmoji()
  }
}
</script>