<template>
  <div class="app">
    <MyButton @click="showModal">Create Post</MyButton>
    <MyModal v-model:show="modalVisilbe">
        <PostForm @create="createPost"/>
    </MyModal>
 
      <PostList 
      :posts="posts" 
      @remove="removePost"
      />
  </div>
  <button @click="fetchUser">Test Button</button>
</template>


<script>
import PostForm from './components/PostForm/PostForm.vue';
import PostList from './components/PostList/PostList.vue';
import axios from 'axios';


export default {
  components: {
    PostForm, PostList
  },

    data() {
      return {
        posts: [],
        modalVisilbe:false
      };
  },
  
  methods: {

    createPost(newPost) {
      this.posts.push(newPost);
      this.modalVisilbe = false;
    },

    removePost(post) {
        this.posts = this.posts.filter(p => p.id !== post.id);
    },

    showModal() {
      this.modalVisilbe = true;
    },

    async fetchUser() {
      try {
        const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
        this.posts = response.data;
        console.log(response.data)
      } catch (error) {
        alert("Error")
      }
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

    .app {
      width: 500px;
      margin: 0 auto;
    }
</style>
