<template>
    <div>
        <dialogPopupCommon :linkImage="alertImage" :message="messagePopup"/>
    </div>
</template>
<script>
import dialogPopupCommon from '../dialogPopupCommon.vue'
export default {
  name:'dialogPopupInfo',
  data(){
    return {
      messagePopup: 'ログアウトします。\nよろしいですか？',
      alertImage: require("@/assets/icon/alert.svg")
    }
  },
  components: {
    dialogPopupCommon
  }
}
</script>