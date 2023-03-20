<template>
    <div>
        <button @click="buttonClick()" :class="[ elicButton ? 'elic-button' : 'cancel-button', 'common-button']">
            <slot></slot>
            {{ buttonName }}
        </button>
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