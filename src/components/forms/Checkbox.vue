<script setup>
import { Check } from 'lucide-vue-next'
import { ref, computed } from 'vue'

const props = defineProps({
    modelValue: { type: [Array, Boolean] },
    id: String,
    label: String,
    value: String
})
const emits = defineEmits(['update:modelValue'])
const isCheck = ref(false)

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
    <label :for="id" class="flex items-center gap-x-2.5">
        <div class="h-4 w-4 flex justify-center items-center overflow-hidden">
            <input type="checkbox" :value="value" v-model="model"
                class="w-full h-full appearance-none border border-neutral-300 rounded-sm checked:bg-blue-600 hover:border-blue-600"
                name="" :id="id">
            <Check :size="14" color="white" :class="['absolute', 'pointer-events-none', { 'hidden': !isCheck }]" />
        </div>
        {{ label }}
    </label>
</template>