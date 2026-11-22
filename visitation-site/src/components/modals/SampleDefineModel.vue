<script setup>

import {defineModel} from "vue";

const v = defineModel('other');

function incrementValue() {
  console.log(v.value);
  v.value += 1;
}

</script>

<template>
 <v-btn @click="incrementValue()">Increment</v-btn>
</template>

<style scoped>

</style>