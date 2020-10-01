<template>
    <section class="progressBarBox">
        <div class="progressBar" 
        v-bind:style="{width: (quotesArray.length * 10) + '%'}">
        </div>
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
    position: relative;
    background-color: #C41286;
}
.progressBar{
    height: 100%;
    background-color: #D90990;
    transition: width 1s ease-in-out;
}
.progressBar__info{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    text-align: center;
}
</style>