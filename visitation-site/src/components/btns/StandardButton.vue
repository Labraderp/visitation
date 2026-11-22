<script setup>
const props = defineProps({
  btnName: {
    type: String,
    required: true
  },
})

function logClick(btnName) {
  console.log(btnName + " was clicked!");
}
</script>

<template>
  <v-btn class="standard-btn"
         variant="outlined"
         size="large"
         :ripple="{class: 'ripple-effect'}"
          @click="logClick(btnName)">
    {{ btnName }}
  </v-btn>
</template>

<style scoped>
.standard-btn {
  background-color: var(--standard-button);
  color: var(--standard-button-text);
}

.standard-btn:hover {
  background-color: var(--standard-button-hover);
  color: var(--standard-button-text);
}

</style>