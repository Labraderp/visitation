<script setup>
import SiteHeader from "./components/SiteHeader.vue";
import ShowCarousel from "./components/ShowCarousel.vue";
import SiteFooter from "./components/SiteFooter.vue";

import { ref } from "vue";
import LoginModal from "./components/modals/LoginModal.vue";

const loginModalOpen = ref(false);
</script>

<template>
 <v-app class="app-override">
   <SiteHeader v-model="loginModalOpen" />
   <v-main class="main-override">
     <LoginModal v-model="loginModalOpen" v-if="loginModalOpen" />
     <ShowCarousel />
   </v-main>
  <SiteFooter />
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