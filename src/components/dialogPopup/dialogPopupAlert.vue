<template>
    <div>
        <baseDialogPopup 
        :linkImage="alertImage" 
        :message="messagePopup"
        :cancelButton="cancelButtonAlert"
        :comfirmButton="comfirmButtonAlert"
        />
    </div>
</template>
<script>
import baseDialogPopup from '../baseDialogPopup.vue'
export default {
  name:'dialogPopupInfo',
  data(){
    return {
      messagePopup: 'ログアウトします。\nよろしいですか？',
      alertImage: require("@/assets/icon/alert.svg"),
      cancelButtonAlert: 'キャンセル',
      comfirmButtonAlert: 'OK'
    }
  },
  components: {
    baseDialogPopup
  }
}
</script>