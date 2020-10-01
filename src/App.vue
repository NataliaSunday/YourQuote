<template>
    <div class="main-container">
        <section class="info">
            <progress-bar :quotesArray="contentOfQuote" ></progress-bar>
            <enter-quote :quotesArray="contentOfQuote" @callingToParent="callingFromChild" ></enter-quote>
        </section>
       <section class="quotes">
            <quote :quotesArray="contentOfQuote"></quote>
       </section>
    </div>
</template>

<script>
import enterQuote from './components/EnterQuote.vue';
import quote from './components/Quote.vue';
import progressBar from './components/ProgressBar.vue';

export default {
    
    components: {
        enterQuote,
        quote,
        progressBar
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
.main-container{
    width: 100vw;
    min-height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #FCEDF7;
    font-size: 16px;
    overflow-x: hidden;
}

.info{
    height: 40vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-around;
   
}

*{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Arizonia;
    color: #FCEDF7;
}
</style>
