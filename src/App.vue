<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Create post</h4>
      <input
          v-bind:value="title"
          @input="title = $event.target.value"
          class="input"
          type="text"
          placeholder="Name">
      <input
          v-bind:value="body"
          class="input"
          @input="body = $event.target.value"
          type="text"
          placeholder="Desc">
      <button class="btn" @click="createPost">Create</button>
    </form>
    <div class="post" v-for="post in posts" :key="post.id">
      <div><strong>Name</strong> {{ post.title }}</div>
      <div><strong>Desc</strong> {{ post.body }}</div>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "",
      body: "",
      posts: [
        {id: 1, title: 'Javascript', body: 'someDescription 1'},
        {id: 2, title: 'TypeScrip', body: 'someDescription 2 '},
        {id: 3, title: 'PHP', body: 'someDescription 3'},
      ]
    }
  },
  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title,
        body: this.body
      }
      this.posts.push(newPost);
      this.title = "";
      this.body = "";
    },
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

.post {
  padding: 15px;
  border: 2px solid darkslategray;
  margin-top: 15px;
}

form {
  display: flex;
  flex-direction: column;
}

.btn {
  margin-top: 10px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: darkslategray;
  border: 1px solid darkslategray;

}

.input {
  width: 100%;
  border: 1px solid darkslategray;
  padding: 10px 15px;
  margin-top: 15px;
}
</style>