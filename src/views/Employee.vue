<template>
  <div>
    <ul v-for="staff in employee" :key="staff.id">
      <router-link :to="{ name: 'staff', params: { id: staff.id } }">
        <li>{{ staff.name }}</li>
      </router-link>
    </ul>
  </div>
</template>
<script>
import { ref } from "@vue/reactivity";
export default {
  setup() {
    const employee = ref([
      {
        id: "emp_001",
        name: "Bopha",
      },
      {
        id: "emp_002",
        name: "Rothana",
      },
      {
        id: "emp_003",
        name: "Sokha",
      },
      {
        id: "emp_004",
        name: "Sokchea",
      },
      {
        id: "emp_005",
        name: "Sokly",
      }
    ]);
    return { employee };
  },
};
</script>
<style></style>
