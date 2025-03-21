<script setup>
import { ChevronDown } from 'lucide-vue-next';
import { ref } from 'vue'
defineProps({
    label: String,
})

const isOpen = ref(true)

const toggle = () => {
    isOpen.value = !isOpen.value
}


</script>

<template>
    <div>
        <div @click="toggle" class="w-full py-1 flex items-center justify-between cursor-pointer">
            <h3 class="text-2xl font-medium">Plateform</h3>
            <ChevronDown :size="20" :class="['transition-transform', { 'rotate-180': isOpen }]" />
        </div>
        <div v-show="isOpen" class="space-y-4 w-full px-2.5 py-4">
            <slot></slot>
        </div>
    </div>
</template>