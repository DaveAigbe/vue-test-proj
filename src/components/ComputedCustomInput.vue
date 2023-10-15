<!-- Cleaner method for component v-model/two way binding -->
<template>
<label for="ComputedCustomInput">Computed component v-model: </label>
<input id="ComputedCustomInput" type="text" v-model="value">
</template>

<script setup>
    import { computed } from 'vue';

    const props = defineProps({
        modelValue: String
    })

    const emit = defineEmits(['update:modelValue'])

    const value = computed({
        get() {
            return props.modelValue
        },
        set(value) {
            emit('update:modelValue', value)
        }
    })
</script>

<style scoped>

</style>