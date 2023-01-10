<template>
    <li class="post">
       <div>
            <p class="post_name"><strong>Title:</strong> {{ post.title }}</p>
            <p class="post_description"><strong>Body:</strong> {{ post.body }}</p>
       </div>

        <div>
            <MyButton 
                class="btn"
                @click="$emit('remove', post)"
                >
                Delete
            </MyButton>
        </div>
    </li>
</template>

<script>

export default {
    props: {
        post: {
            type: Object,
            required: true
        },
    },
}
</script>

<style  scoped>
.post {
    list-style: none;
    padding: 15px;
    width: 500px;
    margin-top: 15px;
    background-color: aqua;
    outline: 3px solid rgba(0, 0, 0, 0);
    border: 2px solid black;
    display: flex;
    align-items: center;
    justify-content: space-between;
}

</style>