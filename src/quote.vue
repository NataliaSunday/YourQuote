<template>
<div class="container">
    <article class="article" v-for="(quote, index) in quotesArray" :key='index' >
        <p class="quote" @click="delate(index)">{{ quote }}</p>    
    </article>   
</div>

</template>

<script>
export default {
    props: {
        quotesArray:{
            type: Array,
            required: true
        }
    },
    methods:{
        delate: function(index){
            this.quotesArray.splice(index, 1);
        }
    }
}
</script>

<style scoped>
.container{
    height: auto;
    max-width: 90vw;
    display: grid;
    grid-template-columns: repeat(4, 25%);
    grid-template-rows: auto;
    grid-gap: 1em;
}
.article{
    width: 100%;
    height: 100%;
    background-color:  #B4E3ED;
    font-size:1.5em;
    font-family: Arizonia;
    padding: .75em;
    letter-spacing: .05em;
    word-wrap:break-word;
    text-align: center;
}

.article:hover{
    background-color: #3CB593;
}

</style>