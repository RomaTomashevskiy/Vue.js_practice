<template>
    <div class="app">
        <h3>List Todo</h3>
        <PostItem v-for="todo in todos" :todo="todo"/>
    </div>
</template>

<script>
import PostItem from './PostItem.vue';

export default {
    props: {
        todos: {
            type: Array,
            required: true
        }
    },
    components: { PostItem }
}
</script>

<style scoped>
.app {
    width: 500px;
    margin: 0 auto;
}
</style>