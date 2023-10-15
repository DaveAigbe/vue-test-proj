<template>
    <div class="login">
        <div>
            <label for="username">Username: </label> 
            <input id="username" type="text" name="email" v-model="usernameValue"> 
        </div>
        <div>
            <label for="password">Password: </label>
            <input id="password" type="text" name="password" v-model="passwordValue">
        </div>
    </div>
</template>

<script setup>
    import { computed } from 'vue';

    const props = defineProps({
        username: String,
        password: String
    })

    const emit = defineEmits(['update:username', 'update:password'])

    const usernameValue = computed({
        get: () => {
            return props.username
        },
        set: (value) => {
            emit('update:username', value)
        }
    })

    const passwordValue = computed({
        get: () => {
            return props.password
        },
        set: (value) => {
            emit('update:password', value)
        }
    })

</script>

<style scoped>
    .login {
        padding: 20px;
        display: flex;
        flex-direction: column;
        gap: 5px;
        background-color: white;
        border-radius: 3px;
        color: black;
    }

</style>