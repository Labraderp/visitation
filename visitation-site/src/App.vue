<script setup>
import SiteHeader from "./components/SiteHeader.vue";
import ShowCarousel from "./components/ShowCarousel.vue";
import SiteFooter from "./components/SiteFooter.vue";
import LoginModal from "./components/modals/LoginModal.vue";
import RegisterModal from "./components/modals/RegisterModal.vue";
import { ref } from "vue";

const loginModalOpen = ref(false);
const registerModalOpen = ref(false);

const userData = ref({
  username: "",
  auth: false,
});

</script>

<template>
 <v-app class="app-override">
   <SiteHeader
       v-model:is-authenticated="userData.auth"
       v-model:login-modal-open="loginModalOpen"
       v-model:register-modal-open="registerModalOpen"/>
   <v-main class="main-override py-lg">
     <LoginModal v-model:user-data="userData"
                 v-model:login-modal-open="loginModalOpen"
                 v-if="loginModalOpen" />
     <RegisterModal v-model="registerModalOpen"
                    v-if="registerModalOpen" />
     <ShowCarousel />
   </v-main>
  <SiteFooter v-model:user-data="userData" class="d-flex py-0"/>
 </v-app>
</template>

<style scoped>

.main-override{
  background-color: #ffffff00
}

.app-override{
  background-color: var(--bg-color);
}

</style>