<template>
    <div>
        <commonDialogPopup 
        :linkImage="infoImage" 
        :cancelButton="cancelButtonInfo"
        :comfirmButton="comfirmButtonInfo"
        @buttonCancel = "InfoButtonCancel()"
        @buttonConfirm = "InfoButtonConfirm()"
        >
          <span class="message-popup">{{ messagePopup }}</span>
        </commonDialogPopup>
    </div>
</template>
<script>
import commonDialogPopup from '../commonDialogPopup.vue'
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
    commonDialogPopup
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