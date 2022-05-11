<template>
  <div>
    <div class="buttons">
      <button @click="handleClick('title')">Title</button>
      <button @click="handleClick('location')">Location</button>
      <button @click="handleClick('salary')">Salary</button>
    </div>
    <ListComponent :jobs="jobs" :order="order" />
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from "vue";

import Job from "./types/Job";
import orderTeam from "./types/OrderTeam";
import ListComponent from "./components/ListComponent.vue";

export default defineComponent({
  name: "App",
  components: { ListComponent },
  setup() {
    const jobs = ref<Job[]>([
      {
        title: "Asadbek",
        location: "Namangan viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 200000,
        id: "1",
      },
      {
        title: "Bobur",
        location: "Andijon viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 120000,
        id: "2",
      },
      {
        title: "Asrorbek",
        location: "Farg'ona viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 210000,
        id: "3",
      },
      {
        title: "Bekzod",
        location: "Toshkent viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 240000,
        id: "4",
      },
      {
        title: "Jamshidbek",
        location: "Guliston viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 200000,
        id: "5",
      },
      {
        title: "Ulug'bek",
        location: "Navoiy viloyati",
        desctiption:
          "      Lorem ipsum dolor sit amet consectetur adipisicing elit. Minima aliquid autem doloremque necessitatibus, quis iure odio esse nulla deserunt numquam dolor excepturi facere, deleniti earum architecto eum libero. Ex dolor iusto facilis hic recusandae deleniti, culpa quaerat doloremque sit ipsa.",
        salary: 200000,
        id: "6",
      },
    ]);
    const order = ref<orderTeam>("title");

    const handleClick = (team: orderTeam) => {
      order.value = team;
    };
    return { jobs, handleClick, order };
  },
});
</script>

<style>
.buttons {
  width: 60%;
  margin: 0 auto;
  text-align: center;
}
.buttons button {
  background-color: green;
  color: white;
  border: none;
  padding: 10px 24px;
  margin: 0 10px;
  cursor: pointer;
  font-size: 20px;
  border-radius: 4px;
  width: 20%;
}
</style>
