<template>
  <div class="app">
    <header>
      <div class="order">
        <button @click="handleClick('title')">title</button>
        <button @click="handleClick('location')">location</button>
        <button @click="handleClick('salary')">salary</button>
      </div>
    </header>
    <jobs-list
      :jobs="jobs"
      :order="order"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";
import JobsList from "./components/JobsList.vue";
import Job from "./types/Job";
import OrderTerm from "./types/OrderTerm";

export default defineComponent({
  name: "App",
  components: { JobsList },
  setup() {
    const jobs = ref<Job[]>([
      { title: "Ship captain", location: "Thessaly", salary: 30000, id: "1" },
      { title: "Prophet", location: "Delphi", salary: 100000, id: "2" },
      { title: "Sculptor", location: "Athens", salary: 30000, id: "3" },
    ]);
    const order = ref("title");

    const handleClick = (term: OrderTerm) => {
      order.value = term;
    };

    return { jobs, handleClick, order };
  },
});
</script>

<style scoped>
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
</style>
