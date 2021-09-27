<template>
  <div>
    <div class="wrapper">
      <img src="@/assets/logo.png" alt="Post image" class="image" />
      <div class="content">
        <h3 class="title">{{ post.title }}</h3>
        <p class="description">{{ post.description }}</p>
      </div>
      <div class="buttons">
        <button class="btn">Favorite</button>
        <button class="btn btn-delete">Remove</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style scoped>
.wrapper {
  margin: 10px 0;
  display: flex;
  align-items: center;
  padding: 15px;
  border: 2px teal solid;
  border-radius: 10px;
}
.image {
  width: 40px;
  height: 40px;
  margin: 0 10px;
}
.content {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  margin: 0 20px;
  width: 100%;
}
.title {
  font-size: 1.5rem;
  font-weight: 700;
  color: teal;
}
.description {
  font-size: 1.2rem;
  font-weight: 400;
  color: grey;
}
.buttons {
  display: flex;
}

.btn ~ .btn {
  margin-left: 5px;
}

.btn {
  border-radius: 10px;
  width: 120px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: black;
  background-color: gold;
  outline: none;
  border: none;
  cursor: pointer;
  font-size: 1rem;
  font-weight: 700;
  transition: 0.15s all ease-in-out;
}

.btn:hover {
  opacity: 0.82;
  box-shadow: 0 0 5px 0 rgba(0, 0, 0, 0.2);
}

.btn-delete {
  background-color: red;
  color: white;
}
</style>
