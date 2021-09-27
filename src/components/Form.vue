<template>
  <form @submit.prevent class="form">
    <h2 class="title">Add new post</h2>
    <input
      v-model="post.theme"
      type="text"
      class="input item"
      placeholder="Type post theme here..."
    />
    <input
      v-model="post.description"
      type="text"
      class="input item"
      placeholder="Now I am thinking about ..."
    />
    <button @click="submitForm" class="btn">Post</button>
  </form>
</template>

<script>
export default {
  name: 'Form',
  data() {
    return {
      post: {
        id: 'default id',
        theme: '',
        description: '',
        favorite: false,
      },
    };
  },

  methods: {
    submitForm() {
      this.post.id = new Date().now().toString();
      this.$emit('create-post', this.post);
      this.post.theme = '';
      this.post.description = '';
    },
  },
};
</script>

<style scoped>
.form {
  margin: 20px 0;
  display: flex;
  flex-direction: column;
}
.title {
  font-size: 1.4rem;
  color: teal;
  font-weight: 700;
  margin-bottom: 15px;
}
.input {
  color: black;
  padding: 10px;
  outline: none;
  font-size: 1.2rem;
  border: 1px grey solid;
  border-radius: 10px;
  margin: 1px;
}
.input:focus {
  border: 2px teal solid;
  margin: 0;
}
.item ~ .item {
  margin-top: 10px;
}
.btn {
  padding: 10px 20px;
  background-color: teal;
  border: none;
  border-radius: 10px;
  margin: 15px 0;
  font-size: 1.2rem;
  color: white;
  cursor: pointer;
}
</style>
