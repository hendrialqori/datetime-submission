<script setup lang="ts">
import { ref, computed } from "vue";
import { format } from "date-fns";

const startDate = ref(format(new Date(), "eee, dd LLL yyyy"));
const endDate = ref(format(new Date(), "eee, dd LLL yyyy"));

const startDateComputed = computed(() =>
  format(new Date(startDate.value), "eee, dd LLL yyyy")
);

const endDateComputed = computed(() => {
  return format(new Date(endDate.value), "eee, dd LLL yyyy");
});
</script>

<template>
  <div
    class="w-4/12 mx-auto flex items-center justify-between border-[1px] rounded-md p-4 mt-5"
  >
    <div class="flex flex-col">
      <span class="text-sm text-gray-500 font-light">Check-in</span>
      <label for="start">{{ startDateComputed }}</label>
      <input v-model="startDate" type="date" id="start" />
    </div>
    <div class="flex flex-col">
      <span class="text-sm text-gray-500 font-light">Check-out</span>
      <label for="end">{{ endDateComputed }}</label>
      <input v-model="endDate" type="date" id="end" />
    </div>
  </div>
</template>
