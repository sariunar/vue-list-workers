<template>
    <div class="modal" v-if="show" @click.stop="hideModal">
        <div @click.stop class="model__content">
            <slot></slot>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        show: {
            type: Boolean,
            default: false
        }
    },
    methods: {
        hideModal() {
            this.$emit('update:show', false);
        }
    } 
}
</script>
<style scoped>
    .modal{
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background: rgba(0, 0, 0, 0.5);
        position: fixed;
        display: flex;
    }
    .model__content{
        margin: auto;
        background: rgb(255, 254, 253);
        border-radius: 12px;
    }
</style>