<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from 'vue'
import { Job } from './types/Job'
import JobList from './components/JobList.vue'

export default defineComponent({
  name: 'App',
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'farm worker', location: 'Karagandy', salary: 30000, id: '1' },
      { title: 'player', location: 'pitch', salary: 100000, id: '2' },
      { title: 'guard', location: 'Rixos', salary: 50000, id: '3' },
      { title: 'fisherman', location: 'lake Baikal', salary: 20000, id: '4' },
    ])

    return { jobs }
  },
})
</script>

<template>
  <div class="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<style></style>
