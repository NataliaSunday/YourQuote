<template>
<section class="progressBarBox">
    <div class="progressBar" v-bind:style="{width: (quotesArray.length * 10) + '%'}"></div>
     <span class="progressBar__info">{{quotesArray.length}} / 10</span>
</section>
    
</template>

<script>
export default {
    props: {
        quotesArray:{
            type: Array,
            required: true
        }
    },
    
}
</script>

<style scoped>
.progressBarBox{
    width: 80vw;
    height: 2em;
    background-color: azure;
    position: relative;
}
.progressBar{
    height: 100%;
    background-color: bisque;
    transition: width 1s ease-in-out;
}
.progressBar__info{
    text-align: center;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
}
</style>