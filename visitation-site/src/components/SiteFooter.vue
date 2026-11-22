<script setup>
import { ref, defineModel } from "vue";

const userData = defineModel('userData',{
  default: () => ({username: '', auth: false}),
});

</script>

<template>
  <div>
      <v-footer app border class="d-flex align-center justify-center">
        <div v-if="userData.auth === true">Welcome to your account, {{ userData.username }}!</div>
        <div v-else>Please log in to access additional directory options!</div>
      </v-footer>
  </div>
</template>

<style scoped>

</style>