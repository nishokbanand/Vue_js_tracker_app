<template>
  <div :key="task.id" v-for="task in tasks">
    <task @toggle-task="this.$emit('toggle-task',task.id)" @delete-task="this.$emit('delete-task',task.id)" :task ="task"/>
  </div>
</template>

<script>
import task from './Task.vue'
export default {
    name : 'Tasks',
    props : {
        tasks : Array,
    },
    components : {
        task
    },
    emits : ['delete-task','toggle-task']
}
</script>
<style scoped>

</style>