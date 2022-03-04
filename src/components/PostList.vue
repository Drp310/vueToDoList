<template lang='pug'>
div
    .post(v-for="post in posts")
            .time time - {{post.time}}
            .deal to deal - {{post.deal}}
            //:id='post.id'
            UIbutton.btn(@click="$emit('deletePost',post)") delete
            
            
</template>

<script>
import UIbutton from '@/components/UI/UIbutton';
export default {
    components:{
        UIbutton
    },
    props:{
        posts:{
            type:Array,
            required: true
        }
    },
    methods:{
        
         
}

}

</script>
<style>
.post{
    border: solid green 2px;
    width: 500px;
    height: 61px;
    margin: 0 auto;
}

</style>