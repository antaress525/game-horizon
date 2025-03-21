<script setup>
import Tag from '@/components/Tag.vue'
import Rating from '@/components/Rating.vue'
import { BoxIcon, ClockIcon, CupSoda } from 'lucide-vue-next';

</script>

<template>
    <div class="bg-white flex gap-x-4 p-2 rounded-lg shadow-2xl group">
        <img src="../assets/forza.jpg" alt="" class="w-45 h-35 object-cover rounded-sm">
        <div class="w-full flex flex-col gap-x-4 gap-y-2">
            <h2
                class="flex items-start justify-between font-bold text-xl transition-colors delay-200 group-hover:text-green-600">
                Forza Horizon 4
                <Rating :rating="8" />
            </h2>
            <div class="flex gap-x-2 items-center">
                <Tag title="Simulation" />
                <Tag title="Arcade" />
                <Tag title="Sport" />
            </div>
            <div class="mt-auto flex justify-between items-center">
                <div class="flex gap-x-2 items-center">
                    <BoxIcon :size="16" />
                    <ClockIcon :size="16" />
                    <CupSoda :size="16" />
                </div>
                <span class="text-black/50 text-sm font-semibold">Jun 15, 2025</span>
            </div>
        </div>
    </div>
</template>