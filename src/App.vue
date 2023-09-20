<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Img from './components/Img.vue'
import BtnNewImage from './components/BtnNewImage.vue'

</script>

<template>
  <header>
    <div class="wrapper">
      <HelloWorld msg="Gerador de imagens em VueJS" />
    </div>
  </header>
  
  <footer class="foot">
    <BtnNewImage />
  </footer>

</template>

<style scoped>
  header {
    text-align: center;
    padding: auto;
    display: block;
  }
   .foot {
    text-align: center;
    padding: auto;
    display: block;
   }
</style>
