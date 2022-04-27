<template>
  <div id="app">
   <Header/>
    <Nuxt />

  </div>
</template>
<script>
// Memanggil component sesuai lokasi masing - masing file
import Header from "@/components/Navbar.vue";
export default {
  // Dideklarasikan agar dapat diakses oleh template
  components: {
    Header

  },
};
</script>
<style>
</style>