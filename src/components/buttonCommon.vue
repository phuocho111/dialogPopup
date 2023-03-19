<template>
    <div>
        <button @click="buttonClick()" :class="[ elicButton ? 'elicButton' : 'cancelButton', 'buttonCommon']">{{ buttonName }}</button>
    </div>
</template>
<script>
export default {
    props: {
        buttonName: {
            type: String,
            default: ''
        },
        elicButton: {
            type: [Boolean, String],
            default: false
        },
    },
    methods: {
        buttonClick() {
            this.$emit('handleCommonButton')
        }
    }
}
</script>
<style lang="scss" scoped>
@import '@/style/desktop.scss';
</style>