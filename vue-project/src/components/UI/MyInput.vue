<template>
    <input :value="value" type="text" class="input" @input="updateValue" >
</template>

<script>
    export default {
        name: "MyInput",
    props: {
        value: [String, Number],
    },

    methods: {
        updateValue(e) { 
            this.$emit("update:value",e.target.value)
        }
    }
    }
</script>

<style  scoped>
.input {
    width: 500px;
    border: 1px solir aqua;
    padding: 10px 15px;
    margin-top: 15px;
}
</style>