<template>
    <div class="dialog-popup">
        <div class="message-area">
            <div class="image-popup">
                <img :src="linkImage" alt="">
            </div>
            <slot></slot>
        </div>
        <div class="button-area">
            <commonButton @handleCommonButton="handleCancelButton()" :buttonName="cancelButton" ></commonButton>
            <commonButton @handleCommonButton="handleConfirmButton()" :buttonName="comfirmButton" elicButton="true" ></commonButton>
        </div>
    </div>
</template>
<script>
import commonButton from './commonButton.vue';
export default {
    components: { commonButton },
    props: {
        linkImage: {
            type: String,
            default: () => ''
        },
        cancelButton: {
            type: String,
            default: () => ''
        },
        comfirmButton: {
            type: String,
            default: () => ''
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