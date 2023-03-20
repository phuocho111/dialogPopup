<template>
    <div class="">
        <button @click="handleShowPopup()">elic Button</button>
        <div class="modal-popup" :hidden="hiddenDialog">
            <dialogPopupInfo 
            @cancelDialog="handleCancelDialog()"
            @confirmDialog="handleConfirmDialog()"
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
            hiddenDialog: true
        }
    },
    components: {
        dialogPopupInfo,
    },
    methods: {
        handleShowPopup() {
            this.hiddenDialog = false
        },
        handleCancelDialog() {
            this.hiddenDialog = true
        },
        handleConfirmDialog() {
            this.hiddenDialog = true
        }
    }
}
</script>
<style lang="scss" scoped>
@import '@/style/desktop.scss';
</style>