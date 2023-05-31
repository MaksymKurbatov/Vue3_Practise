<template>
  <form @submit.prevent>
    <h4>Create post</h4>
    <input
        v-model="post.title"
        class="input"
        type="text"
        placeholder="Name">
    <input
        v-model="post.body"
        class="input"
        type="text"
        placeholder="Desc">
    <button class="btn"
            @click="createPost"
    >
      Create
    </button>
  </form>
</template>

<script>
export default {
  data(){
    return {
      post: {
        title: "",
        body: ""
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post)
      this.post = {
        title: "",
        body: ""
      }
      //this.posts.push(newPost);
    }
  }

}
</script>

<style scoped>
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
