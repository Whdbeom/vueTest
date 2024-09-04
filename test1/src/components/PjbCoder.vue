<template>
    <div>
        <p>header</p>
        <slot name="header" :kossie="kossie"></slot>
        <p>body</p>
        <slot></slot>
        <p>footer</p>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'default title',
        },
        name: {
            type: String,
            default: 'default name',
        },
    },
    data() {
        return {
            kossie : 'Pjb Coder',
        }
    },

    methods: {
        // updateName() {
        //     this.name = 'Pjb Coder Updated';
        // }
    }
}
</script>

<style scoped>

</style>