<template>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary">
          <p>{{ job.salary }} rupees</p>
        </div>

        <div class="description">
          <p>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Ipsa quae officiis et atque!
            Facere, est maxime corrupti voluptatibus autem ipsum, nulla dignissimos dolores nesciunt
            ex placeat iste eos eius libero!
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { type Job } from '../types/Job'

defineProps<{
  jobs: Job[]
}>()

</script>



<style scoped></style>
