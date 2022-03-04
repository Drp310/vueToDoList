<template lang='pug'>
div
    h1 {{name}} - прекрасный человек, его есть за что уважать


    .content
        .main
        input.time(type='text' @input='post.time = $event.target.value' v-bind:value = 'post.time' placeholder='time')
        input.deal(type='text' @input='post.deal = $event.target.value'  v-bind:value = 'post.deal' placeholder='deal')
        UIbutton.newPost(@click="newPost") save
</template>

<script>
import UIbutton from '@/components/UI/UIbutton';
export default {
     components:{
        UIbutton
    },
    props:{
        name:{
            type: String,
            required: true,
        }
    },
    data(){
        return{
            post:{
                time:'',
                deal:'',
                id:Date.now()
            }
        }
},
    methods:{
        newPost(){
            
        this.$emit('create',this.post)
        this.post = {
            time:'',
            deal:'',
            id:''
            
        }       
    },

}
}
</script>

<style>
.content{
    margin: 0 auto;
    border: 3px solid cornflowerblue;
    width: 500px;
}
</style>