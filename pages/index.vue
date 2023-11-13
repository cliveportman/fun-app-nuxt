<script setup lang="ts">

import dayjs from "dayjs";
import duration from "dayjs/plugin/duration";
dayjs.extend(duration);

const { data: activity } = await useFetch('https://fun-api-next.vercel.app/api/activity');
</script>

<template>
  <ul class="text-yellow-200 text-5xl font-bold leading-tight">
    <li>{{ activity.name }}</li>
        <li>{{ (activity.distance / 1000).toLocaleString('en-GB', { minimumFractionDigits: 1, maximumFractionDigits: 1 }) }} km</li>
        <li>{{ dayjs.duration(activity.duration, 'seconds').format('H [hrs] m [min]') }}</li>
  </ul>
</template>