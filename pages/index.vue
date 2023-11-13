<script setup lang="ts">
const { data: activity } = await useFetch('https://fun-api-next.vercel.app/api/activity');
</script>

<template>
  <ul class="text-yellow-200 text-5xl font-bold leading-tight">
    <li>{{ activity.name }}</li>
    <li>{{ activity.distance }}</li>
    <li>{{ activity.duration }}</li>
  </ul>
</template>