<template>
   <div>
        <textarea class="textarea" 
        placeholder="enter your quote" 
        @keyup.enter="callToParent" 
        v-model="content"
        rows="3"
        ></textarea>
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
    data: function(){
        return{
            content: '',
        }
    },
    methods: {
        callToParent(event) {
            if( ( this.content != false ) && ( this.quotesArray.length < 10 ) ){
                alert(this.content);
                this.$emit('callingToParent', this.content);
                this.content = '';
            }
            else if( ( this.content != true ) || ( this.quotesArray.length >= 10 ) ){
                if(this.content == false){
                    alert('Text area is empty');
                } else if( this.quotesArray.length >= 10 ){
                    alert('Too much quotes. You can have ten only');
                }
            }
        }
    }
}
</script>

<style >
.textarea{
    width: 75vw;
    padding: 1em;
    font-size: 2em;
    letter-spacing: .1em;
    border: none;
    outline: none;
    color: #525252;
    resize: none;
}

@media (max-width: 800px){ 
    .textarea{
        width: 90vw;
    }
}

</style>