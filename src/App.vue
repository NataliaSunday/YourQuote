<template>
    <div class="container">
        <enterQuote :name="name"></enterQuote>
    </div>
</template>

<script>
import enterQuote from './enterQuote.vue';

   export default {
    data: function(){
        return{
            name: "Ania",
        }
    }, 
    components: {
        enterQuote
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
