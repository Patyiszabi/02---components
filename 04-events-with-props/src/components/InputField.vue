
<script setup>
    defineEmits(['update:modelValue'])

    defineProps({
        modelValue:{
            type: String,
            default: '',
            required: false
        },
        id: {
            type: String,
            required: true
        },
        type: {
            type: String,
            default: 'text'
        },
        placeholder: {
            type: String,
            default: ''
        },
        label: {
            type: String,
            default: ''
        }
    })

</script>

<template>
    <label :for="id">{{ label }}</label>
    <input
    :value="modelValue"
    :id="id"
    :type="type"
    :placeholder="placeholder"
    @input="$emit('update:modelValue', $event.target.value)" />
</template>

<style scoped>


</style>
