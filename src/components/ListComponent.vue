<template>
  <div>
    <div class="list-group">
      <div
        class="list-group-item"
        v-for="(item, index) in orderJobs"
        :key="index"
      >
        <h2>Title : {{ item.title }}</h2>
        <h3 class="salary">Salaray : {{ item.salary }}</h3>
        <h3>Location : {{ item.location }}</h3>
        <p>{{ item.desctiption }}</p>
        <button class="functionButton" @click="editFucntion(index)">
          Edit
        </button>
        <button class="functionButton" @click="deleteFunction(index)">
          Deleted
        </button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Job from "@/types/Job";
import orderTeam from "@/types/OrderTeam";
import { computed, defineComponent, PropType } from "vue";
export default defineComponent({
  props: {
    jobs: {
      required: true,
      type: Array as PropType<Job[]>,
    },
    order: {
      required: true,
      type: String as PropType<orderTeam>,
    },
  },

  setup(props) {
    const orderJobs = computed(() => {
      return [...props.jobs].sort((a: Job, b: Job) => {
        return a[props.order] < b[props.order] ? 1 : -1;
      });
    });
    const deleteFunction = (id: number) => {
      [...props.jobs].slice(id, 1);
      return props.jobs;
    };
    const editFucntion = (id: number) => {
      alert(id);
    };

    return { orderJobs, deleteFunction, editFucntion };
  },
});
</script>

<style scoped>
.list-group {
  width: 60%;
  margin: 0 auto;
}
.list-group-item {
  box-sizing: border-box;
  background-color: white;
  padding: 20px;
  margin: 20px 0;
  border-radius: 2px;
  transition: all 0.5s;
}
.list-group-item:hover {
  box-shadow: 0 2px 4px black;
  cursor: pointer;
}
.salary {
  color: green;
}
.functionButton {
  color: white;
  font-size: 20px;
  margin-right: 10px;
  background-color: red;
  border-radius: 2px;
  cursor: pointer;
}
.functionButton:nth-child(2n-1) {
  background-color: green;
}
</style>
