<script setup>
import axios from 'axios'
import { ref } from 'vue'
import Img from './Img.vue';

let urlString = ref('')

const height = {
    height: 0
}
const width = {
    width: 0
}

function novaImagem(){
    axios
    .get("https://api.waifu.im/search")
    .then((res) => {

    urlString.value = res.data.images[0].url
    console.log(res.data.images[0].url)

    })
    .catch((error) => {
        console.log(error);
    })
}

novaImagem()

// TODO
// criar opcao de retornar apenas imagesn de largura > altura 
// criar opcao de retornar apenas imagens de altura > largura

function verificaWidth(res) {
    height.height = res.data.images[0].height
    width.width = res.data.images[0].width

    console.log(height)
    console.log(width)

    if (height.height > width.width) {
        console.log("height é maior")
        novaImagem()
    }
    else {
        urlString.value = res.data.images[0].url
        console.log(res.data.images[0].url)
    }
}

</script>

<template>
    <Img :msg="urlString" />
    <button @click="novaImagem" class="button button1">Nova Imagem</button>

</template>

<style>
    .button {
  display: inline-block;
  padding: 15px 25px;
  font-size: 24px;
  cursor: pointer;
  text-align: center;
  text-decoration: none;
  outline: none;
  color: #fff;
  background-color: hsla(160, 100%, 37%, 1);
  border: none;
  border-radius: 15px;
  box-shadow: 0 9px #999;
  margin: 20px;
}

.button:hover {background-color: hsla(160, 100%, 37%, 1);}

.button:active {
  background-color: hsla(160, 100%, 37%, 1);
  box-shadow: 0 5px #666;
  transform: translateY(2px);
}
</style>