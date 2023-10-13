<template>
    <div class="card">
        <h2>{{props.title}}</h2><button @click="increaseFontSize">Enlarge Text</button>
        <div class="card-info">
            <h3>Instructions</h3>
            <p>{{props.instructions}}</p>

            <h3>Ingredients</h3>
            <ul>
                <li v-for="item in props.ingredients" :key="item.id">
                    Name: {{item.name}}
                    <br>
                    Quantity: {{item.quantity}}
                </li>
            </ul>
        </div>
        <hr>
    </div>
</template>

<script setup>

    const props = defineProps({
        title: String,
        instructions: String,
        ingredients:  Array
    })

    const emit = defineEmits(['enlarge-text'])


    function increaseFontSize() {
        emit('enlarge-text')
    }
    
</script>

<style scoped>
    h2 {
        color: green;
    }

    h3 {
        color: lightblue
    }

    p, li {
        color: white;
    }
    .card-info, p {
        padding-left: 50px;
    }
    

    .card {

    }

</style>