<template>
  <v-app>
    <v-main>
      <v-overlay :model-value="overlay" class="align-center justify-center">
        <v-progress-circular color="black" indeterminate size="64"></v-progress-circular>
      </v-overlay>
      <router-view />
      <modal-page />
    </v-main>
  </v-app>
</template>

<script>
import ModalPage from './components/ModalPage.vue';

export default {
  name: "App",
  data: () => ({
    overlay: true,
  }),
  mounted() {
    setTimeout(() => {
      this.overlay = false;
    }, 2000);
  },
  components: {  ModalPage }
}
</script>
