<template>
  <div class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Eco Motivation</h2>
    <div v-if="quote" class="bg-white p-4 rounded shadow italic text-green-800">
      "{{ quote }}"
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue'

const quote = ref<string>('')

onMounted(async () => {
  try {
    const res = await fetch('https://api.quotable.io/random?tags=wisdom|inspirational')
    const data = await res.json()
    quote.value = data.content
  } catch {
    quote.value = "Be the change you wish to see in the world."
  }
})
</script>
