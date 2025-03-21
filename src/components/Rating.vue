<script setup>
import { computed } from 'vue'

const props = defineProps({
    rating: Number,
})

const classes = computed(() => ({
    'text-red-600 bg-red-600/10': props.rating < 5,
    'text-orange-600 bg-orange-600/10': props.rating >= 5 && props.rating < 8,
    'text-green-600 bg-green-600/10': props.rating >= 8,
}))

</script>

<template>
    <span
        :class="['w-8', 'h-8', 'rounded-lg', 'flex', 'items-center', 'justify-center', 'text-sm', 'font-semibold', classes]">
        {{ rating }}
    </span>
</template>