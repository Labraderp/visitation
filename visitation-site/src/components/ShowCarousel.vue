<script setup>
import jayfridPic from '@/imgs/jayfrid com.jpg'
import maxwallpaper from '@/imgs/Max wallpaper.png'
</script>

<template>
  <v-sheet class="d-flex justify-center">
    <v-carousel show-arrows="hover">
      <v-carousel-item
          src="https://cdn.vuetifyjs.com/images/cards/docks.jpg"
          cover>
      </v-carousel-item>

      <v-carousel-item
          :src="jayfridPic"
          cover>
      </v-carousel-item>

      <v-carousel-item
          :src="maxwallpaper"
          cover>
      </v-carousel-item>
    </v-carousel>
  </v-sheet>
</template>

<style scoped>

</style>

export default