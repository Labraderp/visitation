<script setup>
import CancelButton from "@/components/btns/CancelButton.vue";
import ConfirmButton from "@/components/btns/ConfirmButton.vue";
import { ref, defineModel } from "vue";

const loginModalOpen = defineModel({default: true});
const password = ref('');
const showPassword = ref(false);
</script>

<template>
  <v-dialog v-model="loginModalOpen" activator="parent" max-width="600">
    <v-card class="loginModalStyling mx-auto px-6 py-8 align-center" title="Log into your BlurredStripes account">
      <div>
        <v-text-field
          class="mb-2 py-5"
          hide-details="auto"
          label="Username"
          clearable/>
        <v-text-field
          hide-details="auto"
          :type="showPassword ? 'text' : 'password'"
          :append-inner-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
          @click:append-inner="showPassword = !showPassword"
          label="Password" />
        <v-card-actions class="d-flex justify-center align-center py-6">
          <ConfirmButton @click="loginModalOpen = false" btnName="Log In" />
          <CancelButton @click="loginModalOpen = false" btnName="Cancel"/>
        </v-card-actions>
        <v-card-text class="text-center">Forgot your password? Please click <a href="http://localhost:5173">here</a> to submit a reset request.</v-card-text>
      </div>
    </v-card>
  </v-dialog>
</template>

<style scoped>
.loginModalStyling {
  background-color: var(--standard-button);
  color: var(--standard-button-text);
}

</style>