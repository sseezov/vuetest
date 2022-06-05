<template>
  <div class="posts" v-for="post in posts">
    <div class="post">
      <h1>{{ post.title }}</h1>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.posts {
  text-align: center;
}

.post {
  border: 2px solid teal;
  padding: 10px;
  margin: 10px;
}
</style>
