<template>
    <div>
        <baseDialogPopup 
        :linkImage="infoImage" 
        :cancelButton="cancelButtonInfo"
        :comfirmButton="comfirmButtonInfo"
        @buttonCancel = "InfoButtonCancel()"
        @buttonConfirm = "InfoButtonConfirm()"
        >
          <span class="message-popup">{{ messagePopup }}</span>
        </baseDialogPopup>
    </div>
</template>
<script>
import baseDialogPopup from '../baseDialogPopup.vue'
export default {
  name:'dialogPopupInfo',
  data(){
    return {
      messagePopup: 'ログアウトします。\nよろしいですか？',
      infoImage: require("@/assets/icon/info.svg"),
      cancelButtonInfo: 'キャンセル',
      comfirmButtonInfo:'OK'
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
    }
  }
}
</script>