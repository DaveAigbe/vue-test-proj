<!-- Set the inital value to the model-val then each time the input updates emit the event that triggers
the external model to be updated -->
<template>
    <label for="Custom-Input">Component v-model: </label>
    <input id="Custom-Input" type="text" :value="props.modelValue" @input="(e) => updateModelVal(e)" >
</template>

<script setup>

    // Inital value of the model being passed from the parent
    const props = defineProps({
        modelValue: String
    })

    // Method that will automatically update parents model
    const emit = defineEmits(['update:modelValue'])

    function updateModelVal(e) {
        emit('update:modelValue', e.target.value)
    }

</script>

<style scoped>

</style>