<template>
  <div class="min-h-screen bg-green-50 p-6 font-sans">
    <h1 class="text-3xl font-bold text-green-700 mb-6">🌿 GreenHabit</h1>
    <HabitForm @add-habit="addHabit" />
    <HabitList :habits="habits" @delete="deleteHabit" />
    <ProgressBar :habits="habits" />
    <CarbonCalculator :habits="habits" />
    <Quotes />
  </div>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue'
import HabitForm from './components/HabitForm.vue'
import HabitList from './components/HabitList.vue'
import ProgressBar from './components/ProgressBar.vue'
import CarbonCalculator from './components/CarbonCalculator.vue'
import Quotes from './components/Quotes.vue'
import type { Habit } from './types'

const habits = ref<Habit[]>([])

onMounted(() => {
  const saved = localStorage.getItem('habits')
  if (saved) habits.value = JSON.parse(saved)
})

function addHabit(habit: Habit) {
  habits.value.push(habit)
  localStorage.setItem('habits', JSON.stringify(habits.value))
}

function deleteHabit(index: number) {
  habits.value.splice(index, 1)
  localStorage.setItem('habits', JSON.stringify(habits.value))
}
</script>

