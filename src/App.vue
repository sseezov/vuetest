<template>
  <div class="app">
    <h1>Страница с постами</h1>
    <div class="app__btns">
      <my-button @click="showDialog">Создать пост</my-button>
      <my-select v-model="selectedSort" :options="sortOptions"></my-select>
    </div>

    <my-dialog v-model:show="dialogVisible"
      ><post-form @create="createPost"
    /></my-dialog>

    <post-list :posts="posts" @remove="removePost" v-if="!isPostLoading" />
    <div v-else>Идет загрузка</div>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";
import axios from "axios";

export default {
  components: { PostList, PostForm },

  data() {
    return {
      likes: 0,
      posts: [],
      dialogVisible: false,
      isPostLoading: true,
      selectedSort: "",
      sortOptions: [
        {
          value: "title",
          name: "По названию",
        },
        {
          value: "title",
          name: "По описанию",
        },
        {
          value: "title",
          name: "По айди",
        },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
      this.dialogVisible = false;
    },
    removePost(post) {
      this.posts = this.posts.filter((p) => p.id != post.id);
    },
    showDialog() {
      this.dialogVisible = true;
    },
    async fetchPosts() {
      try {
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/posts?_limit=10"
        );
        this.posts = response.data;
        this.isPostLoading = false;
      } catch (e) {
        alert("ошибка: " + e);
      }
    },
  },
  mounted() {
    this.fetchPosts();
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.app {
  display: flex;
  font-size: 20px;
  align-items: center;
  justify-content: center;
  flex-direction: column;
}

.app__btns {
  display: flex;
  justify-content: space-between;
}
</style>
