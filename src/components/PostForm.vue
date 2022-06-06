<template>
  <form @submit.prevent>
    <h1>Создание поста</h1>
    <my-input
      v-model="post.title"
      type="text"      
      placeholder="Названиие поста"
    />
    <my-input
      v-model="post.body"
      type="text"      
      placeholder="Описание поста"
    />
    <my-button class="btn" @click="createPost">Создать</my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: "",
        body: "",
      },
    };
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit("create", this.post);
      this.post = {
        title: "",
        body: "",
      };
    },
  },
};
</script>


