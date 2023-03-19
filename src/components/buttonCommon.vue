<template>
    <div>
        <button @click="buttonClick()" :class="[ elicButton ? 'elicButton' : 'cancelButton', 'button']">{{ buttonName }}</button>
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
        button: {
            type: String,
            default: () =>''
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