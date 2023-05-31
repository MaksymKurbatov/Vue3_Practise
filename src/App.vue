<template>
  <div class="app">
   <post-form
       @create = "createPost"
   />
   <post-list
       :posts="posts"
   />
  </div>
</template>

<script>
import PostForm from "@/components/PostForm/PostForm";
import PostList from "@/components/PostList/PostList";

export default {
  components: {
    PostForm,
    PostList
  },
  data() {
    return {
      posts: [
        {id: 1, title: 'Javascript', body: 'someDescription 1'},
        {id: 2, title: 'TypeScrip', body: 'someDescription 2 '},
        {id: 3, title: 'PHP', body: 'someDescription 3'},
      ]
    }
  },
  methods: {
    createPost(post){
    this.posts.push(post);
    }
  }
}
</script>
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  padding: 20px;
}


</style>