<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
    export default {
        name:'MyButton'
    }
</script>

<style  scoped>
.btn {
            background-color: #c2fbd7;
            border-radius: 100px;
            box-shadow: rgb(44 187 99 / 20%) 0 -25px 18px -14px inset, rgb(44 187 99 / 15%) 0 1px 2px, rgb(44 187 99 / 15%) 0 2px 4px, rgb(44 187 99 / 15%) 0 4px 8px, rgb(44 187 99 / 15%) 0 8px 16px, rgb(44 187 99 / 15%) 0 16px 32px;
            color: green;
            cursor: pointer;
            display: inline-block;
            font-family: CerebriSans-Regular, -apple-system, system-ui, Roboto, sans-serif;
            padding: 7px 20px;
            text-align: center;
            text-decoration: none;
            transition: all 250ms;
            border: 0;
            font-size: 16px;
            user-select: none;
            -webkit-user-select: none;
            touch-action: manipulation;
}
</style>