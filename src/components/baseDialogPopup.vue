<template>
    <div class="dialog-popup" :class="active">
        <div class="title-area" v-if="isTitle">
            <slot name= "contentTitle"/>
        </div>
        <div class="message-area">
            <div class="image-popup">
                <img v-if = "isImage" :src="imageMessage" alt="">
            </div>
            <slot name= "contentMessage"/>
        </div>
        <div class="is-button-area" v-if="isButtonDialog">
            <div v-if="isMutipleButton" class="button-area">
                <baseButton elicButton="button-cancel" @handleCommonButton="handleCancelButton()">{{ cancelButton }}</baseButton>
                <baseButton elicButton="button-elic" @handleCommonButton="handleConfirmButton()">{{ confirmButton }}</baseButton>
            </div>
            <div v-else class="button-area">
                <baseButton @handleCommonButton="handleConfirmButton()" :buttonName="confirmButton" elicButton="button-elic" ></baseButton>    
            </div>
        </div>
        <div v-else class="non-button-area">
            <slot name="contentFooter"/>
        </div>
    </div>
</template>
<script>
import baseButton from './baseButton.vue';
export default {
    components: { baseButton },
    props: {
        isTitle: {
            type: Boolean,
            default: false
        },
        titleName: {
            type: String,
            default: ''
        },
        imageTitle: {
            type: String,
            default: ''
        },
        imageMessage: {
            type: String,
            default: ''
        },
        cancelButton: {
            type: String,
            default: ''
        },
        confirmButton: {
            type: String,
            default: ''
        },
        active: {
            type: String,
            default: ''
        },
        isMutipleButton: {
            type: Boolean,
            default: true
        },
        isImage: {
            type: Boolean,
            default: true
        },
        isButtonDialog: {
            type: Boolean,
            default: true
        },
        content: {
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