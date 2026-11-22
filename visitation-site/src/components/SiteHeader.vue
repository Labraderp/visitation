<script setup>
import {ref, defineModel} from 'vue';
import StandardButton from "./btns/StandardButton.vue";

const loginModalOpen = defineModel('loginModalOpen', {type: Boolean, default: false});
const registerModalOpen = defineModel('registerModalOpen', {type: Boolean, default: false});

function openLoginModal() {
  loginModalOpen.value = true;
  console.log('Setting loginModalOpen to', loginModalOpen.value)
}

function openRegisterModal() {
  registerModalOpen.value = true;
  console.log('Setting registerModalOpen to', registerModalOpen.value)
}

</script>

<template>
  <v-app-bar class="app-header-bar">
    <v-app-bar-nav-icon/>
    <v-app-bar-title>
      Welcome to the Chateau de Stripes and Barks
    </v-app-bar-title>
    <StandardButton v-model="loginModalOpen" btn-name="Log In" @click="openLoginModal" />
    <StandardButton v-model="registerModalOpen" btn-name="Register" @click="openRegisterModal"/>
  </v-app-bar>

</template>

<style scoped>
.app-header-bar {
  background-color: var(--head-foot);
}
</style>

export default