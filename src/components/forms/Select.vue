<script setup>
import { ChevronDown } from 'lucide-vue-next';
import { ref } from 'vue'

defineProps({
    name: String,
    default_label: {
        type: String,
        default: 'Choose me'
    },
    options: Array,
})

const emits = defineEmits(['update:modelValue']);


const selected = ref({ value: null, label: null })
const isOpen = ref(false)
const toggle = () => {
    isOpen.value = !isOpen.value
}
const select = (option) => {
    selected.value = {
        label: option.label,
        value: option.value
    }
    emits('update:modelValue', option.value)
}
</script>

<template>
    <div @click="toggle"
        class="relative select-none flex items-center justify-end bg-gray-400/25 rounded-sm cursor-pointer">
        <div class="w-full py-1 pl-3  cursor-pointer">
            <template v-if="selected.value">
                {{ selected.label }}
            </template>
            <template v-else="selected.value">
                {{ default_label }}
            </template>
        </div>
        <ChevronDown
            :class="['absolute', 'mr-3', 'pointer-events-none', 'transition-transform', { 'rotate-180': isOpen }]"
            :size="16" color="black" />
        <ul v-show="isOpen"
            class="absolute z-10 left-0 right-0 top-10 bg-white shadow-xl border border-black/15 rounded-sm overflow-hidden">
            <li v-for="option in options" :key="option.value"
                @click="select({ label: option.label, value: option.value })"
                class="py-2 px-4 transition-colors delay-100 hover:bg-blue-400 hover:text-white">{{ option.label }}
            </li>
        </ul>
    </div>
</template>