<template>
  <button @click="handleClick('title')">order by title</button>
  <button @click="handleClick('salary')">order by salary</button>
  <button @click="handleClick('location')">order by location</button>
  <JobList :jobs="jobs" :order="order"></JobList>
</template>

<script setup lang="ts">
import { ref } from "vue";
import type Job from "./types/Job";
import JobList from "./components/JobList.vue";
import type OrderTerm from "./types/OrderTerm";
const jobs = ref<Job[]>([
  { title: "farm worker", location: "lon lon ranch", salary: 3000, id: "1" },
  { title: "quarry man", location: "perwez", salary: 4000, id: "2" },
  { title: "flute player", location: "flute land", salary: 6000, id: "3" },
  { title: "dalton", location: "east valley", salary: 7000, id: "4" },
]);

const order = ref<OrderTerm>("title");

const handleClick = (term: OrderTerm) => {
  order.value = term;
};
</script>

<style scoped></style>
