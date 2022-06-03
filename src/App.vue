<template>
  <div class="app">
    <form action="">
      <h1>Создание поста</h1>
    <input type="text" class='input' placeholder="Названиие поста"/>
    <input type="text" class='input' placeholder="Описание поста"/>
    <button class="btn">Создать</button>
    </form>
    <div>Количество лайков:{{ likes }}</div>
    <div class="likes">
      <button class="btn" @click="like">like</button>
      <button class="btn" @click="dislike">dislike</button>
    </div>
    <div class="posts" v-for="post in posts">
      <div class="post">
        <h1>{{ post.title }}</h1>
        <p>{{ post.content }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
      posts: [
        {
          id: 1,
          title: "post1",
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
        {
          id: 2,
          title: "post2",
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
        {
          id: 3,
          title: "post3",
          content:
            "Lorem, ipsum dolor sit amet consectetur adipisicing elit. Cupiditate, sint porro magni doloremque enim ab placeat voluptates expedita suscipit molestiae!",
        },
      ],
    };
  },
  methods: {
    like() {
      this.likes++;
    },
    dislike() {
      this.likes--;
    },
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



.posts {
  text-align: center;
}

.post {
  border: 2px solid teal;
  padding: 10px;
  margin: 10px;
}
.input{
  width: 100%;
  border: 1px solid teal;
  padding: 15px;
  margin-top: 15px;
}
.btn{
  margin: 5px;
  padding: 10px;
  float: right;
}

</style>
