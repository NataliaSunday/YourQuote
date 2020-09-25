<template>
   <div>
        <textarea class="textarea" placeholder="enter your quote" @keyup.enter="callToParent" v-model="content"></textarea>
   </div>
</template>

<script>
export default {
    data: function(){
        return{
            content: '',
        }
    },

    methods: {
        callToParent(event) {
            this.$emit('callingToParent', this.content);
            this.content = '';
        }
    }
 
}
</script>

<style >
.textarea{
    max-width: 50vw;
    min-width: 50vw;
    height: auto;
    font-size:2em;
    border: none;
    outline: none;
    /*
    box-shadow: 2px 4px 10px 10px rgba(255,255,255,.5);
    /*/
    font-family: Arizonia;
    padding: 1em;
    letter-spacing: .1em;
   
   
}
</style>