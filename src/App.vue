<template>
  <div id="app" class="app">
    <VTitle></VTitle>
    <VEmoji></VEmoji>
    <VPiano></VPiano>
  </div>
</template>

<style>
 .app{
   display: flex;
   flex-direction: column;
   align-items: center;
   background: linear-gradient(135deg, #FF9D6C 0%, #BB4E75 100%);
   height: 100vh;
 }
</style>

<script>
import VTitle from '@/components/VTitle'
import VPiano from '@/components/VPiano'
import VEmoji from '@/components/VEmoji'
export default {
  name: 'App',
  components: {
    VTitle,
    VEmoji,
    VPiano
  }
}
</script>