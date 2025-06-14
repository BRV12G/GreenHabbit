<template>
  <div class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Weekly Progress</h2>
    <div class="w-full bg-gray-200 rounded-full h-4">
      <div class="bg-green-600 h-4 rounded-full transition-all duration-500" :style="{ width: progress + '%' }"></div>
    </div>
    <p class="text-sm text-gray-600 mt-1">{{ progress }}% habits done this week</p>
  </div>
</template>

<script lang="ts" setup>
import { computed } from 'vue'
import type { Habit } from '../types'

const props = defineProps<{
  habits: Habit[]
}>()

const progress = computed(() => {
  const count = props.habits.length
  const weeklyGoal = 7
  return Math.min(Math.round((count / weeklyGoal) * 100), 100)
})
</script>
