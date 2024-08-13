<template>
    <div>
      <!-- <button @click="getPosts">Load Posts</button> -->
      <h2 v-if="errorMsg">Error Messafe - {{ errorMsg }}</h2>
      <div v-for="post in posts" :key="post.id">
          <h4>Id - {{ post.id }}</h4>
          <h4>Title - {{ post.title }}</h4>
          <h6>Body - {{ post.body }}</h6>
      </div>
      <br>
      <!-- <button @click="posts=[]">Close Posts</button> -->
    </div>
  </template>
  
  <script>
  import axios from "axios";
  export default {
    name: "RequestOnLoad",
    created(){
        this.getPosts();
    },
    data() {
      return {
        posts: [],
        errorMsg: ''
      };
    },
    methods: {
      getPosts() {
        axios
        .get("https://jsonplaceholder.typicode.com/posts")
        .then((response) => {
            console.log(response.data);
            this.posts = response.data;
          })
          .catch((error) => {
            console.log(error);
            this.errorMsg = 'Error Retrieving posts'
          });
      },
    },
  };
  
  </script>
  
  <style scoped>
  </style>