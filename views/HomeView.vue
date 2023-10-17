<template>
    <div class="home">
      <h1>Hom</h1>
      <postList :posts="posts" />
  
    </div>
  </template>
  
  <script>
  import postList from '../components/postList.vue';
  import getPost from '@/components/getPost.js';
  
  export default {
    name: 'Home',
    components: { postList },
    setup(){
      const { posts, error, load } = getPost()
      
      load()
      return{ posts, error}
  }
  }
  </script>
  
  <style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
  </style>
  