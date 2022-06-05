<template>
  <div class="posts">
    <div class="post">
      <h1>{{ post.title }}</h1>
      <div class="postButtons">
        <my-button class="btn">Удалить</my-button>
      </div>
      <p>{{ post.body }}</p>
    </div>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {
    MyButton,
  },

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
  border: 2px solid teal;
  padding: 10px;
  margin: 10px;
}
</style>
