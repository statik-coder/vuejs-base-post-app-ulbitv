<template>
  <div v-for="post in posts" :key="post.id">
    <post :post="post" />
  </div>
</template>

<script>
import Post from '@/components/Post';

export default {
  name: 'PostsList',
  components: { Post },
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style></style>
