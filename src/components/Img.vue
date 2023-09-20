<script setup>

const props = defineProps({
    msg: String
})
</script>

<template>
    <div class="box">
        <img :src="msg" alt="imagem"/>
    </div>
</template>

<style scoped>
    .box {
        background-color: rgba(0, 255, 149, 0.034);
        width: 500px;
        height: 500px;
        border-radius: 15px;
        border: 4px solid hsla(160, 100%, 37%, 1);
        margin: auto;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    img {
        max-height: 98%;
        max-width: 98%;
    }    
</style>