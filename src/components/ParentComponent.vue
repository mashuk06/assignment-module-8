<script setup>
    import ChildComponent from './ChildComponent.vue';
    import { ref } from 'vue'

    const parentMessage = ref('Hello from Parent')
    const emittedMessage = ref('')

    const handleChildMessage = (message) => {
        emittedMessage .value = message
    }
</script>

<template>
    <div class="min-h-screen flex items-center justify-center bg-gray-100">
        <div class="bg-white p-6 rounded-lg shadow-md">
            <h2 class="text-xl my-3">Parent Component</h2>
            <ChildComponent :message="parentMessage" @message-emitted="handleChildMessage" />
            <p class="mt-4">Received message from child: {{ emittedMessage }}</p>
        </div>
    </div>
</template>
