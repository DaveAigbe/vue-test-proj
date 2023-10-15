<template>
    <input type="checkbox" v-model="checkboxVal" @change="updateIsChecked">
</template>

<script setup>
    import { ref } from 'vue';

    const props = defineProps({
        isChecked: Boolean
    })

    const emit = defineEmits(['updateIsChecked'])

    const checkboxVal = ref(props.isChecked)

    function updateIsChecked() {
        emit('updateIsChecked', checkboxVal.value)
    }
</script>

<style scoped>

</style>