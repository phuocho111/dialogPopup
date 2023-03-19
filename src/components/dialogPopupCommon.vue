<template>
    <div class="dialog-popup">
        <div class="message-area">
            <div class="image-popup">
                <img :src="linkImage" alt="">
            </div>
            <span class="message-popup">{{ message }}</span>
        </div>
        <div class="button-area">
            <button-common @handleCommonButton="handleCancelButton()" :buttonName="cancelButton" ></button-common>
            <button-common @handleCommonButton="handleConfirmButton()" :buttonName="comfirmButton" elicButton="true" ></button-common>
        </div>
    </div>
</template>
<script>
import buttonCommon from './buttonCommon.vue';
export default {
    components: { buttonCommon },
    props: {
        message: {
            type: String,
            default: ''
        }, 
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