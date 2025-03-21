<script setup>
defineProps({
    title: String,
})

</script>

<template>
    <span class="px-2.5 py-0.5 rounded-sm font-medium text-[12px] bg-neutral-200">
        {{ title }}
    </span>
</template>