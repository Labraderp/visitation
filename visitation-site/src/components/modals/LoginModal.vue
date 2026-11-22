<script setup>
import CancelButton from "@/components/btns/CancelButton.vue";
import { ref, defineModel } from "vue";
import ConfirmButton from "@/components/btns/ConfirmButton.vue";

const loginModalOpen = defineModel({default: true});
const password = ref('');
const showPassword = ref(false);
</script>

<template>
  <v-dialog v-model="loginModalOpen" activator="parent" max-width="600">
    <v-card class="loginModalStyling" title="Log into your RetardMaxxing Account">
      <v-text-field
        hide-details="auto"
        label="Username" />
      <v-text-field
        hide-details="auto"
        :type="showPassword ? 'text' : 'password'"
        :append-inner-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
        @click:append-inner="showPassword = !showPassword"
        label="Password" />
      <v-card-actions class="d-flex justify-center align-center">
        <ConfirmButton @click="loginModalOpen = false" btnName="Log In" />
        <CancelButton @click="loginModalOpen = false" btnName="Cancel"/>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<style scoped>
.loginModalStyling {
  background-color: var(--standard-button);
  color: var(--standard-button-text)
}
</style>