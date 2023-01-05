<template>
    <div class="app">
        <h2>Create Post</h2>
        <form class="form" @submit.prevent>
            <MyInput 
            v-model:value="todo.name" 
            placeholder="Name..." 
            class="input" 
            />
            <MyInput 
            v-model:value="todo.description" 
            placeholder="Description..." 
            class="input" 
            />
            <MyButton type="submit" class="btn" @click="createPost">Create</MyButton>
        </form>
    </div>
</template>

<script>
import MyButton from './UI/MyButton.vue';
import MyInput from './UI/MyInput.vue';


export default {
    components: {
        MyButton, MyInput
    },
    
    data() {
        return {
            todo: {
                name: "",
                description: ""
            },
        };
    },
    methods: {
        createPost() {
            if (this.todo.name.trim() === "") {
                return alert(`Please ,enter name your post`);
            }
            else if (this.todo.description.trim() === "") {
                return alert(`Please ,enter description your post`);
            }
            ;
            this.todo.id = new Date();
            this.todo.isDone = false;
            this.$emit("create", this.todo);
            this.todo = {
                name: "",
                description: ""
            };
        },
    },
    components: { MyButton }
}   
</script>



<style scoped>
.app {
    width: 500px;
    margin: 0 auto;
}

.form {
    display: inline-block;
    display: flex;
    flex-direction: column;
}


.btn {
    margin-top: 10px;
    padding: 10px 15px;
    align-self: flex-end;
    background: none;
    color: aqua;
    cursor: pointer;
    border: 1px solid aqua;
}

.btn:hover {
    background-color: rgb(156, 255, 255);
    color: #ffff;
}
</style>