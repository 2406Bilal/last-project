<template>
  <div class="home">
    <h1>Home</h1>
    <h1>it works after that i refresh the localhost</h1>
    <div v-if="error">{{ error }}</div>
    <div v-if="posts">
      <postList :posts="posts" />
    </div>
    <div v-else>loading .....</div>
  </div>
</template>

<script>
import postList from './components/postList.vue';
import getPost from './components/singlePost.vue';

export default {
  name: 'Home',
  components: { postList },
  setup() {
    const { posts, error, load } = getPost;
    if (!posts) {
      load;
    }
    return { posts, error };
  }
};
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