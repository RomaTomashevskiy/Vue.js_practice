<template>
    <div>
        <button class="delete_btn">
            <slot></slot>
        </button>
    </div>
</template>

<script>
    export default {
        name:'MyButton'
    }
</script>

<style  scoped>
    .delete_btn {
            padding: 5px 10px;
            background: rgb(5, 175, 218);
            cursor: pointer;
        }
</style>