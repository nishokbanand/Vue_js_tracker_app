<template>
  <div
    @dblclick="ToggleRemainder(id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <h3>
      {{ task.text }} <br />
      {{ task.Day }}
      <i @click="OnDelete(task.id)" class="fas fa-times"> </i>
    </h3>
  </div>
</template>

<script>
export default {
  name: "task",
  props: {
    task: Object,
  },
  methods: {
    OnDelete(id) {
      this.$emit("delete-task", id);
    },
    ToggleRemainder(id) {
      this.$emit("toggle-task", id);
    },
  },
};
</script>
<style scoped>
i {
  color: red;
}

.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>