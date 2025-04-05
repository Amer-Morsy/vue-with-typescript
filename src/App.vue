<template>
  <div class="app">
    <!-- <p>{{ name }} {{ age }}</p>
    <button @click="changeName('Zelda')">change name</button>
    <button @click="changeAge('34')">change age</button> -->
    <h1>Jobs</h1>
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }}</h2>
        <p>Location: {{ job.location }}</p>
        <p>Salary: {{ job.salary }}</p>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, ref, toRefs } from "vue";
import Job from "@/types/Job";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    // const state = reactive({
    //   name: "Link",
    //   age: 25 as number | string,
    // });
    // // state.name = 999; // This will throw an error because name is expected to be a string
    // state.age = 30;
    // return { ...toRefs(state) };

    // const name = ref("Link");
    // // const age = ref(25 as number | string);
    // const age = ref<number | string>(25);
    // return {
    //   name,
    //   age,
    // };

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
  methods: {
    // changeName(name: string) {
    //   this.name = name;
    // },
    // changeAge(age: number) {
    //   this.age = age;
    // },
  },
});
</script>

<style></style>
