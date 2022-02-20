<template lang='pug'>
.wrapper
  post-form
  post-list(:posts='posts')

</template>

<script>
import PostForm from '@/components/PostForm';
import PostList from '@/components/PostList';

export default {
    components:{
        PostForm,PostList
    },
data(){
    return{
        likes:0,
        posts:[
            {time:'14:30', deal:'visit shop',id:1},
            {time:'00:00',deal:'sleep',id:2},
            {time:'00:00',deal:'sleep',id:3},    
            ],
        DoTime:'',
        DoDeal:'',
    }
},
methods:{
    postAmountAdd(){
       
    },
    newPost(){
        this.likes++;
        this.posts.push({time:this.DoTime, deal:this.DoDeal,id:this.likes+3});
        this.DoTime = '';
        this.DoDeal = '';
       
    },
    deletePost(){
        console.log(this.posts)
    }

}

     
 
}
</script>

<style>
.post{
    border: solid green 2px;
    width: 150px;
    height: 61px;
}
</style>