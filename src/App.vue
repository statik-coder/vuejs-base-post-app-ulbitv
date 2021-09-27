<template>
  <div class="containter">
    <h1 class="app-title">Base Post app on Vue.js</h1>
    <post-form @create-post="createPost" />
    <post-list :posts="posts" />
  </div>
</template>

<script>
import PostList from '@/components/PostsList';
import PostForm from '@/components/Form';

export default {
  name: 'App',
  components: { PostList, PostForm },

  data() {
    return {
      posts: [
        {
          id: Date.now().toString(),
          title: 'This is first post',
          description: "Ohh... vue it's awesome. I really like it!",
          favorite: false,
        },
        {
          id: (Date.now() + 1).toString(),
          title: 'This is second post',
          description: "Yeah... of course I feel some difficulties but it's ok",
          favorite: false,
        },
      ],
    };
  },

  methods: {
    createPost(post) {
      this.posts.push(post);
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.containter {
  margin: 15px;
}

.app-title {
  margin: 0 auto;
  text-align: center;
  font-size: 1.8rem;
  color: #2c3e50;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
