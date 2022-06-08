<template>
  <div class="app">
    <post-form @create="createPost" />
    <post-list :posts="posts" @remove="removePost"/>
  </div>
</template>

<script>
import PostForm from "@/components/PostForm";
import PostList from "@/components/PostList";

export default {
  components: { PostList, PostForm },

  data() {
    return {
      likes: 0,
      posts: [
        {
          id: 1,
          title: "post1",
          body: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
        {
          id: 2,
          title: "post2",
          body: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
        {
          id: 3,
          title: "post3",
          body: "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
      ],
    };
  },
  methods: {
    createPost(post) {
      this.posts.push(post);
    },
    removePost(post){
      this.posts=this.posts.filter(p=>p.id!=post.id)
    }
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
</style>
