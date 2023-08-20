<script setup>
import { defineEmits, ref } from 'vue'

defineProps(['message'])
defineEmits(['childMessage'])

const customMessage = "This is a message from child"

</script>

<template>
  <div class="bg-gray-200 p-4 rounded-lg">
    <h2 class="text-xl">Child Component</h2>
    <p class="text-gray-700 font-bold">Received message from parent: </p>
    <p class="text-gray-600">{{ message }}</p>
    <button class="mt-2 px-4 py-2 bg-blue-500 text-white rounded" @click="$emit('messageEmitted', customMessage)">Emit Message</button>
  </div>
</template>


