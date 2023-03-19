<template>
    <div>
        <dialogPopupCommon 
        :linkImage="alertImage" 
        :message="messagePopup"
        :cancelButton="cancelButtonAlert"
        :comfirmButton="comfirmButtonAlert"
        />
    </div>
</template>
<script>
import dialogPopupCommon from '../dialogPopupCommon.vue'
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
    dialogPopupCommon
  }
}
</script>