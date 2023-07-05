<template>
  <v-col cols="auto">
    <v-dialog v-model="showModal" transition="dialog-top-transition" width="350" height="250">
      <v-card>
        <v-toolbar color="black" title="Order Now for Event's Photography" style="border-bottom:2px solid #E91E63 ;"></v-toolbar>
        <v-card-text>
          <h1 class="text-subtitle-1 pa-5 pb-10 pt-10">Hello! Welcome to Our Website.</h1>
        </v-card-text>
      </v-card>
    </v-dialog>
  </v-col>
</template>

<script>
export default {
  data() {
    return {
      showModal: false
    };
  },
  mounted() {
    // Show the modal after a delay of 10 seconds (10000 milliseconds)
    setTimeout(() => {
      this.showModal = true;
    }, 10000);//10 sec
  },
};
</script>
