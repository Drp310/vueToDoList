<template lang='pug'>
.wrapper
  post-form(:name='name'
            @create='newPost'
  )
  post-list(:posts='posts'
            @deletePost='deletePost'
  )
 
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
        name:'Arseniy',
    }
},
methods:{
    postAmountAdd(){
       
    },
    newPost(post){
        this.likes++;
        this.posts.push(post);
        
       
    },
    deletePost(post){
        console.log(post.time)
        this.posts = this.posts.filter(i=>i.id!==post.id)
        
    }

}

     
 
}
</script>

<style>
.post{
    border: solid green 2px;
    width: 500px;
    height: 61px;
}
</style>