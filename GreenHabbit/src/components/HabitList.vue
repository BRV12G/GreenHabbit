<template>
  <div class="mb-6">
    <h2 class="text-xl font-semibold mb-2">Your Habits</h2>
    <ul class="space-y-2">
      <li v-for="(habit, index) in habits" :key="index" class="flex justify-between bg-white p-3 rounded shadow">
        <span>{{ habit.text }}</span>
        <button @click="$emit('delete', index)" class="text-red-500 hover:underline">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import type { Habit } from '../types'

defineProps<{
  habits: Habit[]
}>()

defineEmits<{
  (e: 'delete', index: number): void
}>()
</script>
