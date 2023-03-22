<template>
    <div class="dialog-popup" :class="active">
        <div class="message-area">
            <div class="image-popup">
                <img :src="linkImage" alt="">
            </div>
            <slot></slot>
        </div>
        <div class="button-area">
            <baseButton @handleCommonButton="handleCancelButton()" :buttonName="cancelButton" ></baseButton>
            <baseButton @handleCommonButton="handleConfirmButton()" :buttonName="comfirmButton" elicButton="true" ></baseButton>
        </div>
    </div>
</template>
<script>
import baseButton from './baseButton.vue';
export default {
    components: { baseButton },
    props: {
        linkImage: {
            type: String,
            default: ''
        },
        cancelButton: {
            type: String,
            default: ''
        },
        comfirmButton: {
            type: String,
            default: ''
        },
        active: {
            type: String,
            default: ''
        }
    },
    methods: {
        handleCancelButton() {
            this.$emit('buttonCancel')
        },
        handleConfirmButton() {
            this.$emit('buttonConfirm')
        }
    }
}
</script>
<style lang="scss" scoped>
@import '@/style/desktop.scss';
</style>