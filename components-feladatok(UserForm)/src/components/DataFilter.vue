<script setup>
    const data = [
    { id: 1, name: 'John Doe' },
    { id: 2, name: 'Jane Doe' },

    { id: 3, name: 'Jim Smith' },
    { id: 4, name: 'Sarah Johnson' },
    ]
</script>

<template>
    <input v-model="name" type="text"  @input="$emit('on-input', name)"/>
    
</template>

<style scoped></style>
