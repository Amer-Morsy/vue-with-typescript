<template>
  <div class="app">
    <header>
      <div class="title">
        <img src="./assets/heart.svg" alt="site logo" />
        <h1>Hyrule Jobs</h1>
      </div>
      <div class="order">
        <button @click="handelClick('title')">Order by title</button>
        <button @click="handelClick('salary')">Order by salary</button>
        <button @click="handelClick('location')">Order by location</button>
      </div>
    </header>

    <JobList :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import Job from "@/types/Job";
import JobList from "@/components/JobList.vue";
import OrderTerm from "@/types/OrderTerm";

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

    const order = ref<OrderTerm>("title");

    const handelClick = (term: OrderTerm) => {
      order.value = term;
    };
    return {
      jobs,
      order,
      handelClick,
    };
  },
});
</script>

<style>
header {
  text-align: center;
}
header .order {
  margin-top: 20px;
}
button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
}
header .title {
  display: flex;
  justify-content: center;
}
header img {
  width: 60px;
  margin-right: 20px;
}
header h1 {
  font-size: 3em;
}
</style>
