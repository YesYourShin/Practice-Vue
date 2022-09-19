<template>
    <li>
        {{ todo.text }}
        {{ todo.check ? "체크" : "No"}}
        {{ todo.time }}
        <button @click="$emit('remove', todo.id)">X</button>
        <button @click="$emit('check', todo.id)">V</button>
        
    </li>
</template>

<script>
export default {
    props: {
        todo: {
            type: Object,
            required: true,
        }
    },
}
</script>