<template>
    <div class="">
        <button @click="handleShowPopup()">elic Popup</button>
        <div class="modal-popup" v-show="showDialog">
            <dialogPopupInfo 
            @cancelDialog="handleCancelDialog()"
            @confirmDialog="handleConfirmDialog()"
            :showPopup="openPopup ? 'popup-open' : 'popup-close'"
            />
        </div>
    </div>
</template>
<script>
import dialogPopupInfo from './dialogPopup/dialogPopupInfo.vue';
export default {
    name:'elicAi',
    data() {
        return {
            showDialog: false,
            openPopup: false,
            ShowAlert: false
        }
    },
    components: {
        dialogPopupInfo,
    },
    methods: {
        handleShowPopup() {
            this.showDialog = true
            this.openPopup = true
        },
        handleCancelDialog() {
            this.openPopup = false
            setTimeout(() => {
                this.showDialog = false
            }, 500);
        },
        handleConfirmDialog() {
            this.openPopup = false
            setTimeout(() => {
                this.showDialog = false
            }, 500);
        },
    }
}
</script>
<style lang="scss" scoped>
@import '@/style/desktop.scss';
</style>