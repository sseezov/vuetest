<template>
  <form @submit.prevent>
    <h1>Создание поста</h1>
    <input
      v-model="post.title"
      type="text"
      class="input"
      placeholder="Названиие поста"
    />
    <input
      v-model="post.body"
      type="text"
      class="input"
      placeholder="Описание поста"
    />
    <button class="btn" @click="createPost">Создать</button>
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

<style scoped>
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 15px;
  margin-top: 15px;
}
.btn {
  margin: 5px;
  padding: 10px;
  float: right;
  background: none;
  border: 1px solid teal;
  cursor: pointer;
}
</style>
