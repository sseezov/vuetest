<template>
  <div class="posts">
    <div class="post">
      <h1>{{ post.title }}</h1>      
      <p>{{ post.body }}</p>
      <div class="postButtons">
        <my-button class="btn" @click="$emit('remove', post)">Удалить</my-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
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
  display: flex;
  flex-direction: column;
  border: 2px solid teal;
  padding: 10px;
  margin: 10px;
  min-height: 80px;
}
</style>
