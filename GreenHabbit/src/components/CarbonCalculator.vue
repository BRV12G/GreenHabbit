<template>
  <div class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Carbon Footprint Saved</h2>
    <p class="text-lg bg-white p-4 rounded shadow">
      You've saved an estimated <span class="font-bold text-green-700">{{ carbonSaved }}kg</span> of CO₂ 🌎
    </p>
  </div>
</template>

<script lang="ts" setup>
import { computed } from 'vue'
import type { Habit } from '../types'

const props = defineProps<{
  habits: Habit[]
}>()

const carbonSaved = computed(() => {
  return (props.habits.length * 0.7).toFixed(2)
})
</script>
