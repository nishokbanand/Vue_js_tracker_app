<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @btn-click="this.$emit('btn_click')"
      :title="showAddTasks ? 'Close' : 'AddTask'"
      :color="showAddTasks ? 'red' : 'green'"
    />
  </header>
</template>
<script>
import Button from "./Button.vue";
export default {
  name: "Header",
  props: {
    title: String,
    showAddTasks: Boolean,
  },
  components: {
    Button,
  },
};
</script>
<style>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>