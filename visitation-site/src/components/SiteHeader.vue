<script setup>
import {ref, defineModel} from 'vue';
import StandardButton from "./btns/StandardButton.vue";
import CancelButton from "./btns/CancelButton.vue";

const loginModalOpen = defineModel('loginModalOpen', {type: Boolean, default: false});
const registerModalOpen = defineModel('registerModalOpen', {type: Boolean, default: false});
const isAuthenticated = defineModel('isAuthenticated', {default: false});

function openLoginModal() {
  loginModalOpen.value = true;
  console.log('Setting loginModalOpen to', loginModalOpen.value)
}

function openRegisterModal() {
  registerModalOpen.value = true;
  console.log('Setting registerModalOpen to', registerModalOpen.value)
}

function logOut() {
  isAuthenticated.value = false;
  loginModalOpen.value = false;
  console.log('Logging out...');
}
</script>

<template>
  <v-app-bar class="app-header-bar">
    <v-app-bar-nav-icon/>
    <v-app-bar-title>
      Welcome to the Chateau de Stripes and Wags
    </v-app-bar-title>
    <StandardButton v-if="isAuthenticated === false" v-model="loginModalOpen" btn-name="Log In" @click="openLoginModal" />
    <StandardButton v-if="isAuthenticated === false" v-model="registerModalOpen" btn-name="Register" @click="openRegisterModal"/>
    <CancelButton v-if="isAuthenticated === true" v-model="isAuthenticated" btn-name="Log Out" @click="logOut" />
  </v-app-bar>

</template>

<style scoped>
.app-header-bar {
  background-color: var(--head-foot);
}
</style>

export default