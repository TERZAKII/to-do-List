<script setup lang="ts">
import { ref } from 'vue'
import { type Job } from './types/Job'
import JobList from './components/JobList.vue'

const jobs = ref<Job[]>([
  { title: 'farm worker', location: 'Karagandy', salary: 30000, id: '1' },
  { title: 'player', location: 'pitch', salary: 100000, id: '2' },
  { title: 'guard', location: 'Rixos', salary: 50000, id: '3' },
  { title: 'fisherman', location: 'lake Baikal', salary: 20000, id: '4' },
])

const title = ref('')
const location = ref('')
const salary = ref(0)

const currentId = ref(5)

const setNewJob = (job: Job) => {
  jobs.value.unshift(job)
  title.value = ''
  location.value = ''
  salary.value = 0
}
</script>

<template>
  <div class="app">
    <input type="text" v-model="title" />
    <input type="text" v-model="location" />
    <input type="number" v-model="salary" />
    <button
      @click="
        setNewJob({
          title: title,
          location: location,
          salary: salary,
          id: `${currentId++}`,
        })
      "
    >
      +
    </button>
    <JobList :jobs="jobs" />
  </div>
</template>

<style></style>
