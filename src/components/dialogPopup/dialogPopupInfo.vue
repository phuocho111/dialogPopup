<template>
    <div>
        <dialogPopupCommon 
        :linkImage="infoImage" 
        :message="messagePopup"
        :cancelButton="cancelButtonInfo"
        :comfirmButton="comfirmButtonInfo"
        @buttonCancel = "InfoButtonCancel()"
        @buttonConfirm = "InfoButtonConfirm()"
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
      infoImage: require("@/assets/icon/info.svg"),
      cancelButtonInfo: 'キャンセル',
      comfirmButtonInfo:'OK'
    }
  },
  components: {
    dialogPopupCommon
  },
  methods: {
    InfoButtonCancel() {
      console.log('cancel')
    },
    InfoButtonConfirm() {
      console.log('OK')
    }
  }
}
</script>