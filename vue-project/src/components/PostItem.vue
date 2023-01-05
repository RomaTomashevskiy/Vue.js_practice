<template>
    <li class="post">
       <div>
            <p class="post_name"><strong>Name:</strong> {{ todo.name }}</p>
            <p class="post_description"><strong>Description:</strong> {{ todo.description }}</p>
       </div>

        <div>
            <MyButton>Delete</MyButton>
        </div>
    </li>
</template>

<script>
import MyButton from './UI/MyButton.vue';

export default {
    components: {
        MyButton
    },
    props: {
        todo: {
            type: Object,
            required: true
        },
    },
    components: { MyButton }
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
.delete_btn{
        padding: 5px 10px;
        background: rgb(5, 175, 218);
        cursor: pointer;
    }
</style>