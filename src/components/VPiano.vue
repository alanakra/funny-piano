<template>
<div class="all">
 <div class="container-piano">
  <div class="bg-white" id="key-do"></div>
  <div class="bg-white" id="key-re"></div>
  <div class="bg-white" id="key-mi"></div>
  <div class="bg-white" id="key-fa"></div>
  <div class="bg-white" id="key-sol"></div>
  <div class="bg-white" id="key-la"></div>
  <div class="bg-white" id="key-si"></div>

  <div class="container-bg-black">
   <div class="bg-black" id="A-b"></div>
   <div class="bg-black" id="B-b"></div>
   <div class="bg-black" id="C-b"></div>
   <div class="bg-black" id="D-b"></div>
   <div class="bg-black" id="E-b"></div>
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
  mounted(){

    const keyDo = document.querySelector('#key-do')
    const keyRe = document.querySelector('#key-re')
    const keyMi = document.querySelector('#key-mi')
    const keyFa = document.querySelector('#key-fa')
    const keySol = document.querySelector('#key-sol')
    const keyLa = document.querySelector('#key-la')
    const keySi = document.querySelector('#key-si')
    const bemol1 = document.querySelector('#A-b')
    const bemol2 = document.querySelector('#B-b')
    const bemol3 = document.querySelector('#C-b')
    const bemol4 = document.querySelector('#D-b')
    const bemol5 = document.querySelector('#E-b')
    
    keyDo.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/C.mp3'
      audio.play()
    })

    keyRe.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/D.mp3'
      audio.play()
    })

    keyMi.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/E.mp3'
      audio.play()
    })
    
    keyFa.addEventListener('click', () =>{  
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/F.mp3'
      audio.play()
    })

    keySol.addEventListener('click', () =>{  
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/G.mp3'
      audio.play()
    })

    keyLa.addEventListener('click', () =>{  
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/A.mp3'
      audio.play()
    })

    keySi.addEventListener('click', () =>{  
      const audio = document.createElement('audio')
      audio.src = 'assets/sounds/B.mp3'
      audio.play()
    })

    bemol1.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = encodeURIComponent('assets/sounds/C#.mp3')
      audio.play()
    })

    bemol2.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = encodeURIComponent('assets/sounds/D#.mp3')
      audio.play()
    })

    bemol3.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = encodeURIComponent('assets/sounds/F#.mp3')
      audio.play()
    })

    bemol4.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = encodeURIComponent('assets/sounds/G#.mp3')
      audio.play()
    })

    bemol5.addEventListener('click', () =>{
      const audio = document.createElement('audio')
      audio.src = encodeURIComponent('assets/sounds/A#.mp3')
      audio.play()
    })

  }
}

</script>