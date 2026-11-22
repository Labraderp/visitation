<script setup>
import CancelButton from "@/components/btns/CancelButton.vue";
import ConfirmButton from "@/components/btns/ConfirmButton.vue";
import { ref, defineModel } from "vue";

const registerModalOpen = defineModel({default: true});
const password = ref('');
const validatedPassword = ref('');

const showPassword = ref(false);
const showValidatedPassword = ref(false);
</script>

<template>
  <v-dialog v-model="registerModalOpen" activator="parent" max-width="600">
    <v-card class="registerModalStyling mx-auto px-6 py-8 align-center" title="Create your BlurredStripes account">
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
            label="Enter a password." />
        <v-text-field
            hide-details="auto"
            :type="showValidatedPassword ? 'text' : 'password'"
            :append-inner-icon="showValidatedPassword ? 'mdi-eye' : 'mdi-eye-off'"
            @click:append-inner="showValidatedPassword = !showValidatedPassword"
            label="Enter the password again." />
        <v-card-actions class="d-flex justify-center align-center py-6">
          <ConfirmButton @click="registerModalOpen = false" btnName="Submit" />
          <CancelButton @click="registerModalOpen = false" btnName="Cancel"/>
        </v-card-actions>
      </div>
    </v-card>
  </v-dialog>
</template>

<style scoped>
.registerModalStyling {
  background-color: var(--standard-button);
  color: var(--standard-button-text);
}

</style>