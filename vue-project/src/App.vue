<template>
    <div>
      <PostForm @create="createPost"/>
      <PostList :todos="todos"/>
    </div>
</template>


<script>
import PostForm from './components/PostForm.vue';
import PostList from './components/PostList.vue';

import todos from './data/todos.json';

export default {
  components: {
    PostForm, PostList
  },
    data() {
      return {
        todos
      }
  },
  methods: {

    createPost(newPost) {
      this.todos.push(newPost);
    },

  },
     
  }
</script>


<style>
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  
</style>
