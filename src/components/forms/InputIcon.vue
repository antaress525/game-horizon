<script setup>
import { computed } from 'vue'
import { Search } from 'lucide-vue-next';

const props = defineProps({
    modelValue: String,
})
const emits = defineEmits(['update:modelValue']);
const model = computed({
    get() {
        return props.modelValue;
    },
    set(value) {
        emits("update:modelValue", value);
    },
});

</script>

<template>
    <div class="relative flex items-center bg-gray-400/25 rounded-sm">
        <Search class="absolute ml-3 pointer-events-none" :size="16" color="black" />
        <input type="text" v-model="model" placeholder="God of war" class="w-full outline-0 py-1 pl-8.5 pr-3">
    </div>
</template>