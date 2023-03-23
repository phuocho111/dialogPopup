<template>
    <div>
        <baseDialogPopup 
        :imageMessage="infoImage" 
        :cancelButton="cancelButtonInfo"
        :confirmButton="confirmButtonInfo"
        :active="showPopup"
        :isImage="true"
        :isMutipleButton="true"
        @buttonCancel = "InfoButtonCancel()"
        @buttonConfirm = "InfoButtonConfirm()"
        >
        <template v-slot:contentMessage><span class="message-popup">{{ messagePopup }}</span></template>
        </baseDialogPopup>
    </div>
</template>
<script>
import baseDialogPopup from '../baseDialogPopup.vue'
export default {
  name:'dialogPopupInfo',
  data(){
    return {
      messagePopup: 'ログアウトします。\n よろしいですか？',
      infoImage: require("@/assets/icon/info.svg"),
      cancelButtonInfo: 'キャンセル',
      confirmButtonInfo:'OK'
    }
  },
  props: {
    showPopup: {
      type: Boolean,
      default:  true
    }
  },
  components: {
    baseDialogPopup
  },
  methods: {
    InfoButtonCancel() {
      this.$emit('cancelDialog')
    },
    InfoButtonConfirm() {
      this.$emit('confirmDialog')
    },
  }
}
</script>