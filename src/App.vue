<template>
    <div><div >Количество лайков:{{ likes }} </div>
    <button @click="like">like</button>
    <button @click="dislike">dislike</button>
    
    </div>

  
</template>

<script>
export default {
  data() {
    return {
      likes: 0,
    }
  },
  methods: {
    like(){
      this.likes++
    },
    dislike(){
      this.likes--
    }
  }
};
</script>

<style></style>
