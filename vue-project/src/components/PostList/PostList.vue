<template>
    <div>
        <h3>List Posts</h3>
        <PostItem 
        v-for="post in posts" 
        :post="post" 
        :key="post.id"
        @remove="$emit('remove', post)"
        />
    </div>
</template>

<script>
import PostItem from '../PostItem/PostItem.vue';

export default {
    components: { PostItem },
    
    props: {
        posts: {
            type: Array,
            required: true
        }
    },
}
</script>

<style scoped>

</style>