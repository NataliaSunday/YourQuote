<template>
    <div class="container">
        <article class="article" 
        v-for="(quote, index) in quotesArray" :key='index' >
            <p @click="delate(index)">{{ quote }}</p>    
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
    width: 90vw;
    height: min-content;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-template-rows: min-content;;
    grid-gap: 1em;

}
.article{
    width: 100%;
    height: min-content;
    padding: .75em;
    background-color: #D90990;
    font-size: 1.5em;
    text-align: center;
    letter-spacing: .05em;
    word-wrap: break-word;
    cursor: pointer;
    transition: background-color .25s linear;
}

.article:hover{
    background-color: #3CB593;
}

 @media (max-width: 800px) and (orientation: landscape){ 
    .container{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }
}
 @media (max-width: 800px){ 
    .container{
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }
}

</style>