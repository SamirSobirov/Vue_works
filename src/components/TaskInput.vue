<template>
  <div class="task-input my-list">
    <input
      class="bg-gray-800"
      v-model="title"
      placeholder="Title"
      type="text"
    />
    <input
      class="bg-gray-800"
      v-model="description"
      placeholder="Description"
      type="text"
    />
    <button class="bg-gray-600" @click="onAddTask">Add task</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  emits: ["onAddTask"],
  setup(props, { emit }) {
    const title = ref("");
    const description = ref("");

    const onAddTask = () => {
      if (title.value === "" || description.value === "") {
        alert("Fill some fields please!");
        return;
      }
      emit("onAddTask", { title: title.value, description: description.value });
    };

    return {
      title,
      description,
      onAddTask,
    };
  },
};
</script>

<style scoped>
.task-input {
  margin: 10px 0;
}
</style>
