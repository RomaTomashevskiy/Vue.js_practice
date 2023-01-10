<template>
    <input :value="value" type="text"  @input="updateValue" >
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
    
</style>