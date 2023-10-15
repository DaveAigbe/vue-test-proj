<template>
    <ul class="list">
        <li v-for="(val, index) in props.listValues" :key="index">{{val}}</li>
    </ul>
</template>

<script setup>
const props = defineProps({
    listValues: Array
})
        
</script>

<style scoped>
    .list {
        max-height: 150px;
        overflow: auto;
        background-color: white;
        color: black;
        border-radius: 4px;
        margin-top: 4px;
    }
</style>