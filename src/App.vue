<template>
    <div class="container">
        <enterQuote @callingToParent="callingFromChild"></enterQuote>
        <quote :quotesArray="contentOfQuote"></quote>
    </div>
</template>

<script>

import enterQuote from './EnterQuote.vue';
import quote from './Quote.vue';

export default {
    
    components: {
        enterQuote,
        quote
    },
    data() {
        return{
            contentOfQuote: []
        }
    },
    methods: {
        callingFromChild (value){
            this.contentOfQuote.push(value);
             console.log('dryn'+ value );
        }
    }
}
</script>

<style>
.container{
    width: 100vw;
    height: 100vh;
    background-color: #88F1FC;
    font-size: 16px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}
*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>
