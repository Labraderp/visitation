<script setup>
defineProps({
  btnName: String,
  default: "New Button"
})
</script>

<template>
  <v-btn class="cancel-btn"
         variant="outlined"
         size="x-large"
         :ripple="{class: 'ripple-effect'}">
    {{ btnName }}
  </v-btn>
</template>

<style scoped>
.cancel-btn {
  background-color: var(--cancel-button);
  color: var(--cancel-button-text);
}

.cancel-btn:hover {
  background-color: var(--cancel-button-hover);
  color: var(--cancel-button-text);
}

.cancel-btn:hover :deep(.v-btn__overlay){
  opacity: 0;
}
</style>