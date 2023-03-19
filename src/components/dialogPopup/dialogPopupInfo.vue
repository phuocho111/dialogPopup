<template>
    <div>
        <dialogPopupCommon :linkImage="infoImage" :message="messagePopup"/>
    </div>
</template>
<script>
import dialogPopupCommon from '../dialogPopupCommon.vue'
export default {
  name:'dialogPopupInfo',
  data(){
    return {
      messagePopup: 'ログアウトします。\nよろしいですか？',
      infoImage: require("@/assets/icon/info.svg")
    }
  },
  components: {
    dialogPopupCommon
  }
}
</script>