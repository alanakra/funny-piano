<template>
<div class="all">
 <div class="container-piano">
  <div class="bg-white" v-for="note in white" :key="`key${note.name}`" :id="`key${note.name}`" @click="launchNote(note)" :data-keycode="note.keyCode"></div>

  <div class="container-bg-black">
   <div class="bg-black" v-for="note in black" :key="`key${note.name}`" :id="`key${note.name}`" @click="launchNote(note)" :data-keycode="note.keyCode"></div>
  </div>

 </div>

  <div class="text-clavier">
    <p>DO</p>
    <p>RE</p>
    <p>MI</p>
    <p>FA</p>
    <p>SOL</p>
    <p>LA</p>
    <p>SI</p> 
  </div>
</div>

</template>

<style>
 .container-piano{
  background-color: #000000;
  border-radius: 10px;
  height: 276px;
  width: 531px;
  margin-top: 59px;
  display: flex;
  justify-content: space-between;
  padding: 10px;
  position: relative;
 }

 .bg-white {
  width: 69px;
  cursor: pointer;
}
.bg-white:nth-child(1){
  border-radius: 5px 0px 0px 5px;
}
.bg-white:nth-child(7){
  border-radius: 0px 5px 5px 0px;
}
.bg-white:active{
  background: #FFD12D;
}

.bg-black {
  height: 184px;
  width: 30px;
  border-radius: 0px 0px 5px 5px;
  z-index: 1;
  position: absolute;
  cursor: pointer;
}
.bg-black:active{
  background-color: #E6016F;
}

.bg-black:nth-child(1){
  left: 66px;
}
.bg-black:nth-child(2){
  left: 140px;
}
.bg-black:nth-child(3){
  left: 285px;
}
.bg-black:nth-child(4){
  left: 358px;
}
.bg-black:nth-child(5){
  left: 431px;
}

.text-clavier{
  display: flex;
  color: white;
  justify-content: space-around;
  font-family: 'PT-Mono', monospace;
}

@media (max-width: 414px) {
 .container-piano{
  width: 368px;
  height: 189.33px;
 }

 .bg-white{
  width: 47.82px;
  height: 172.87px;
 }

 .bg-black{
  width: 20.79px;
  height: 126.22px;
  left: 40px;
 }

 .bg-black:nth-child(1){
  left: 50px;
 }

 .bg-black:nth-child(2){
   left: 100px;
 }

 .bg-black:nth-child(3){
   left: 200px;
 }

 .bg-black:nth-child(4) {
  left: 250px;
 }

 .bg-black:nth-child(5) {
  left: 300px;
 }

}
</style>

<script>
export default {
  data(){
    return{
      white : [
        {
          name :'do',
          sound : 'C',
          keyCode: 81
        },
        {
          name :'re',
          sound : 'D',
          keyCode: 83
        },
        {
          name :'mi',
          sound : 'E',
          keyCode: 68
        },
        {
          name :'fa',
          sound: 'F',
          keyCode: 70
        },
        {
          name: 'sol',
          sound: 'G',
          keyCode: 71
        },
        {
          name: 'la',
          sound: 'A',
          keyCode: 72
        },
        {
          name: 'si',
          sound: 'B',
          keyCode: 74
        }
      ],
      black: [
        {
          name:'do#',
          sound: 'C#',
          keyCode: 90
        },
        {
          name: 're#',
          sound: 'D#',
          keyCode: 69
        },
        {
          name :'fa#',
          sound: 'F#',
          keyCode: 84
        },
        {
          name: 'sol#',
          sound: 'G#',
          keyCode: 89
        },
        {
          name: 'la#',
          sound: 'A',
          keyCode: 85
        },
      ],
    }
  },

  mounted(){

     console.log(this)
     this.vEmoji = this.$parent.$children[1]
     this.audio = document.createElement('audio')
     document.addEventListener('keydown', (e) => {
       console.log(e.keyCode)
       const el = this.$el.querySelector(`[data-keycode="${e.keyCode}"`)
       console.log(el)
       if(el){
         el.click();
       }
     })
  },

   methods: {
    launchNote(note){
      console.log(note)
      const name = encodeURIComponent(note.sound)
      this.audio.src = `/assets/sounds/${name}.mp3`
      this.audio.play();
      this.vEmoji.callEmoji()
    }
  }
}

</script>