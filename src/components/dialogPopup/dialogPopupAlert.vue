<template>
    <div>
        <baseDialogPopup 
        :imageMessage="alertImage" 
        :message="messagePopup"
        :confirmButton="confirmButtonAlert"
        :active="showAlert"
        :isMutipleButton="false"
        @buttonConfirm="AlertButtonConfirm"
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
      messagePopup: 'ログアウトします。\n よろしいですか。',
      alertImage: require("@/assets/icon/alert.svg"),
      confirmButtonAlert: 'OK'
    }
  },
  props: {
    showAlert: {
      type: Boolean,
      default:  true
    }
  },
  components: {
    baseDialogPopup
  },
  methods: {
    AlertButtonConfirm(){
      this.$emit('confirmAlert')
    }
  }
}
</script>