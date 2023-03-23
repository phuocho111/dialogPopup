<template>
    <div>
        <button @click="buttonClick()" :class="[ elicButton , 'common-button']">
            <slot></slot>
        </button>
    </div>
</template>
<script>
export default {
    props: {
        elicButton: {
            type: String,
            default: ''
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