<template>
    <div class="container">
        <enterQuote  @callingToParent="callingFromChild"></enterQuote>
    </div>
</template>

<script>
import enterQuote from './enterQuote.vue';

export default {
    components: {
        enterQuote
    },
    data:{
        contentOfQuote: ''
    },
    methods: {
        callingFromChild (value){
            this.contentOfQuote = value;
             console.log('dryn'+ value );
        }
    }
}
</script>

<style>
.container{
    width: 100vw;
    height: 100vh;
    background-color: #B4EDEA;
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
