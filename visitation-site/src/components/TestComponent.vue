<script setup>
import {ref} from 'vue'
const count = ref('')

function increment() {
  count.value++
}

defineProps({
  name: {
    type: String,
    required: true,
  },

  count: {
    type: Number,
    default: 0
  }
})

</script>

<template>
    <h1> {{ name }} </h1>
    <v-app>
        <v-btn variant="tonal" @click="increment" size="large">
          {{ count }}
        </v-btn>
    </v-app>

</template>

<style scoped>

</style>

export default Test