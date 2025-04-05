<template>
  <div class="app">
    <JobList :jobs="jobs" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "@/types/Job";
import JobList from "@/components/JobList.vue";

export default defineComponent({
  name: "App",
  components: { JobList },
  setup() {
    const jobs = ref<Job[]>([
      {
        id: "1",
        title: "Software Engineer",
        location: "Remote",
        salary: 30000,
      },
      {
        id: "2",
        title: "Data Scientist",
        location: "Remote",
        salary: 40000,
      },
      {
        id: "3",
        title: "Product Manager",
        location: "Remote",
        salary: 50000,
      },
    ]);

    return {
      jobs,
    };
  },
});
</script>

<style></style>
