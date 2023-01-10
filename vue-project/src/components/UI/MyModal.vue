<template>
    <div class="modal-overlay" v-if="show" @click.stop="isHideModal">
        <div @click.stop class="modal"><slot></slot></div>
    </div>
</template>

<script>
export default {
    name: 'MyModal',

    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        isHideModal() {
            this.$emit('update:show', false)
        },
    }
};
</script>

<style scoped>
.modal {

     display: block;

     padding: 15px;
     width: 600px;
     max-width: 100%;

     max-height: 100%;

     position: fixed;

     z-index: 100;

     left: 50%;
     top: 50%;

     transform: translate(-50%, -50%);

    border-radius: 15px;
     background: white;
     box-shadow: 0 0 60px 10px rgba(0, 0, 0, 0.9);
 
 }


 .modal-overlay {
     position: fixed;
     top: 0;
     left: 0;
     width: 100%;
     height: 100%;
     z-index: 50;

     background: rgba(0, 0, 0, 0.6);
 }

 * {
     box-sizing: border-box;
     margin: 0;
     padding: 0;
 }
</style>