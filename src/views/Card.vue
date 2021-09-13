<template>
  <div class="flex justify-between px-4 mt-4 sm:px-8">
    <h2 class="text-2xl text-gray-600">Card</h2>
    <div class="flex items-center space-x-1 text-xs">
      <router-link to="/" class="font-bold text-indigo-700">Home</router-link>
      <svg xmlns="http://www.w3.org/2000/svg" class="h-2 w-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
      </svg>
      <span class="text-gray-600">Card</span>
    </div>
  </div>
  <div class="px-4 mt-8 sm:px-8">
    <CardStacked />
    <hr />
    <CardHorizontal />
  </div>
</template>

<script>
import { CardHorizontal, CardStacked } from '@/components/UI/Card'

export default {
  components: {
    CardHorizontal,
    CardStacked,
  },
}
</script>
