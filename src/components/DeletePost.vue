<template>
  <div>
    <h1>Delete Post</h1>
    <form @submit.prevent="deletePost">
      <div>
        <button type="submit">Delete</button>
      </div>
    </form>
    <h3 v-if="message">{{ message }}</h3>
    <h3 v-if="errorMessage">{{ errorMessage }}</h3>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  name: "DeletePost",
  data() {
    return {
      message: "",
      errorMessage: ""
    };
  },
  methods: {
    deletePost() {
        axios
        .delete('https://jsonplaceholder.typicode.com/posts/1')
        .then((response)=> {
            console.log(response);
            this.message = 'Post deleted successfully';
        })
        .catch((error)=> {
            console.log(error);
            this.errorMessage = 'Error deleting post';
        })
    },
  },
};
</script>

<style scoped>
</style>