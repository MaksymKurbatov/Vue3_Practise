<template>
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Name</strong> {{ post.title }}</div>
      <div><strong>Desc</strong> {{ post.body }}</div>
    </div>
</template>

<script>
export default {
 props: {
   posts: {
     type: Array,
     required: true
   }
 }
}
</script>

<style scoped>
.post {
  padding: 15px;
  border: 2px solid darkslategray;
  margin-top: 15px;
}
</style>