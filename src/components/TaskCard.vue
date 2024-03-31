<script setup lang="ts">
import { ref } from 'vue';

defineProps<{ title: string, desc: string }>()

const shortenSentence = (sentence: string): string => {
  const words = sentence.split(' ')
  if (words.length <= 15) {
    return sentence
  } else {
    words[14].replace(',', '')
    return words.slice(0, 15).join(' ') + '...'
  }
};

const showIcon = ref(false)
</script>

<template>
  <div
    class="relative w-full min-h-20 max-h-28 px-2 py-1 border-teal-200 border-l-4 shadow hover:shadow-md rounded text-gray-500"
    @mouseover="showIcon = true"
    @mouseleave="showIcon = false"
  >
    <p class="font-semibold text-ellipsis overflow-x-hidden">{{title}}</p>
    <p class="break-words text-ellipsis overflow-y-hidden">{{shortenSentence(desc)}}</p>
    <font-awesome-icon v-show="showIcon" class="absolute right-2 bottom-2 cursor-pointer text-gray-300 hover:text-gray-400 " icon="pen" />
  </div>
</template>
