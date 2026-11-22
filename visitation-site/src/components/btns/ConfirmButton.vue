<script setup>

defineProps({
  btnName: String,
  default: "New Button"
})
</script>

<template>
  <v-btn class="confirm-btn"
         variant="outlined"
         size="x-large"
         :ripple="{class: 'ripple-effect'}">
    {{ btnName }}
  </v-btn>
</template>

<style scoped>
  .confirm-btn {
    background-color: var(--confirm-button);
    color: var(--confirm-button-text);
  }

  .confirm-btn:hover {
    background-color: var(--confirm-button-hover);
    color: var(--confirm-button-text);
  }

  .confirm-btn:hover :deep(.v-btn__overlay){
    opacity: 0;
  }

</style>