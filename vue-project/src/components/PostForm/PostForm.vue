<template>
    <div class="app">
        <h2>Create Post</h2>
        <form class="form" @submit.prevent>
            <MyInput 
            v-model:value.trim="todo.title" 
            placeholder="Name..." 
            class="input" 
            />
            <MyInput 
            v-model:value.trim="todo.body"  
            placeholder="Description..." 
            class="input" 
            />
            <MyButton type="submit" class="btn" @click="createPost">Create</MyButton>
        </form>
    </div>
</template>

<script>

export default {
    data() {
        return {
            todo: {
                title: "",
                body: ""
            },
        };
    },
    methods: {
        createPost() {
            if (this.todo.title === "") {
                return alert(`Please ,enter name your post`);
            }
            else if (this.todo.body === "") {
                return alert(`Please ,enter description your post`);
            }
            ;
            this.todo.id = new Date();
            this.$emit("create", this.todo);
            this.todo = {
                title: "",
                body: ""
            };
        },
    },

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
.input {
    width: 500px;
    border: 1px solir aqua;
    padding: 10px 15px;
    margin-top: 15px;
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