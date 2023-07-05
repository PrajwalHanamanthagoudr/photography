<template>
  <section id="contact">
    <v-container class="py-8 lg:py-12 xl:py-16">
      <v-row class="flex-wrap flex-row-reverse mt-10 mb-10 justify-space-around">
        <v-col cols="12" md="6">
          <div>
            <h1 class="text-h3 text-decoration-overline">Location</h1>
            <h4 class="text-h6 mt-5">Gadag,KA India</h4>
          </div>
        </v-col>
        <iframe class="w-full h-full" id="gmap_canvas" style="height: 30rem; width: 60rem;"
          src="https://maps.google.com/maps?q=Karnataka&t=&z=10&ie=UTF8&iwloc=&output=embed" frameborder="0"
          scrolling="no" marginheight="0" marginwidth="0">
        </iframe>
        <v-col cols="12" sm="6">
        </v-col>
      </v-row>
    </v-container>
  </section>
</template>
  
<script>
export default {
  name: 'LocationPage',
};
</script>
  
<style></style>
  