<script setup lang="ts">
defineProps<{ title: string }>()
</script>

<template>
    <div class="flex flex-col gap-4 w-80">
        <!-- Board Column Title -->
        <div class="flex items-center justify-between w-full h-11 px-2 py-1 border-teal-300 border-t-4 shadow rounded uppercase font-bold text-gray-500">
            <p>{{title}}</p>
            <font-awesome-icon class="text-teal-300 cursor-pointer" icon="plus" />
        </div>
        <slot></slot>
    </div>
</template>