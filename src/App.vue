
<template>
  <main>
    <TaskInput></TaskInput>
    <TaskCard> </TaskCard>
  </main>


</template>



<script>
import TaskInput from './components/TaskInput.vue';
import TaskCard from './components/TaskCard.vue';

  export default {
    name: 'App',
    components: {
      TaskCard,
      TaskInput
    }
  }
</script>

