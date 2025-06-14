<template>
  <form @submit.prevent="submitHabit" class="mb-4">
    <input v-model="habit" placeholder="Enter eco-habit..." class="border rounded p-2 w-full mb-2" required />
    <button class="bg-green-600 text-white px-4 py-2 rounded hover:bg-green-700">Add Habit</button>
  </form>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import type { Habit } from '../types'

const emit = defineEmits<{
  (e: 'add-habit', habit: Habit): void
}>()

const habit = ref<string>('')

function submitHabit() {
  if (!habit.value.trim()) return
  emit('add-habit', { text: habit.value, date: new Date().toISOString() })
  habit.value = ''
}
</script>
