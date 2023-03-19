<template>
    <div class="dialog-popup">
        <div class="message-area">
            <div class="image-popup">
                <img :src="linkImage" alt="">
            </div>
            <span class="message-popup">{{ message }}</span>
        </div>
        <div class="button-area">
            <button-common :buttonName="cancelButton" ></button-common>
            <button-common :buttonName="comfirmButton" elicButton="true" ></button-common>
        </div>
    </div>
</template>
<script>
import buttonCommon from './buttonCommon.vue';
export default {
    data (){
        return {
            cancelButton: 'キャンセル',
            comfirmButton: "OK"
        }
    },
    components: { buttonCommon },
    props: {
        message: {
            type: String,
            default: ''
        }, 
        linkImage: {
            type: String,
            default: () => ''
        }
    }
}
</script>
<style lang="scss" scoped>
@import '@/style/desktop.scss';
</style>