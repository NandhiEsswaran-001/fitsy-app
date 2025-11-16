<script setup>
  import Layout from "./components/layouts/Layout.vue";
  import Welcome from "./components/pages/Welcome.vue"
  import Dashboard from "./components/pages/Dashboard.vue"
  import Workout from "./components/pages/Workout.vue"

  import { ref } from 'vue'

  const selectedDisplay = ref(3)
  const data = ref()
  const selectedWorkout = ref(-1)
  
</script>

<template>
  <Layout>
    <!-- Page 1 -->
      <Welcome v-if="selectedDisplay == 1" />
    <!-- Page 2 -->
      <Dashboard v-if="selectedDisplay == 2" />
    <!-- Page 3 -->
      <Workout v-if="selectedDisplay == 3" />
  </Layout>
</template>

<style scoped>

</style>
