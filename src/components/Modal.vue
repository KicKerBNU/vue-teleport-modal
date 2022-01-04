<template lang="pug">
div.backdrop(@click.self="closeModal")
    .modalScoped(:class="{ sale: theme === 'sale' }")
        slot default content
        div.actions
            slot(name="links")

</template>

<script>
export default {
    props: ['theme'],
    methods: {
        closeModal() {
            this.$emit('close')
        }
    }
}
</script>

<style scoped>
    .modalScoped{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop {
        top: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }
</style>