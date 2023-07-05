<template>
  <section style="background-color:rgb(0, 0, 0)" id="contact">
      <v-container class="py-8 lg:py-12 xl:py-16" style="color: white;">
          <v-row class="flex-wrap flex-row-reverse mt-10 mb-10 ml-10">
              <v-btn v-for="icon in icons" :key="icon" class="mx-4" :icon="icon" href="#" variant="text">
                  <v-icon size="34px" color="#1877f2">{{ icon }}</v-icon>
              </v-btn>
              <v-col cols="12" md="6" class="mt-10">
                  <div style="line-height: 2rem;" @click="scrollToTop">
                      <h4 class="white--text pb-2">Our Services</h4>
                      <p class="white--text">&#183; Product Photography</p>
                      <p class="white--text">&#183; Event Photography</p>
                      <p class="white--text">&#183; Portrait Photography</p>
                  </div>

              </v-col>
              <v-col class="ml-16">
                  <div style="line-height: 2rem;" @click="scrollToTop">
                      <h4 class="white--text pb-2">Useful Links</h4>
                      <p class="white--text">&#183; Home</p>
                      <p class="white--text">&#183; About us</p>
                      <p class="white--text">&#183; Services</p>
                      <p class="white--text">&#183; Gallery</p>
                      <p class="white--text">&#183; Contact Us</p>
                  </div>
              </v-col>
              <div style="line-height: 2rem;">
                  <h4 class="white--text pb-2">Contact Information</h4>
                  <p>
                      <v-icon color="white">mdi-map-marker</v-icon>
                      Address: Gadag, Karnataka 582101
                  </p>
                  <p>
                      <v-icon color="white">mdi-phone</v-icon>
                      Phone: +919731156771
                  </p>
                  <p>
                      <v-icon color="white">mdi-email</v-icon>
                      Email: PrajwalHanamanthagoudr@gmail.com
                  </p>
              </div>
              <v-col cols="12" sm="6">

              </v-col>
          </v-row>
      </v-container>
      <v-btn icon="mdi-arrow-up" v-if="showBackToTop" fixed bottom="5" right="5"
          class="fixed-button bg-black hover:bg-blue text-white" @click="scrollToTop"
          style="  position: fixed; bottom: 20px; right: 20px; z-index: 999; border-radius: 50%;"></v-btn>
  </section>
  <section style="background-color:#E3F2FD" class="pa-3">
      <div class="d-flex justify-space-around">
          <span>
              © Copyright Prajwal. All Rights Reserved
          </span>
          <span>
              Designed by <a href="https://github.com/PrajwalHanamanthagoudr">Prajwal Hanamanthagoudr</a>
          </span>
      </div>
  </section>
</template>

<script>
export default {
  name: 'FooterPage',
  data() {
      return {
          showBackToTop: false,
          icons: [
              'mdi-facebook',
              'mdi-twitter',
              'mdi-linkedin',
              'mdi-instagram',
          ],
      }
  },
  methods: {
      scrollToTop() {
          window.scrollTo({ top: 0, behavior: 'smooth' });
      },
      handleScroll() {
          this.showBackToTop = window.scrollY > 0;
      },
  },
  mounted() {
      window.addEventListener('scroll', this.handleScroll);
  },
  beforeUnmount() {
      window.removeEventListener('scroll', this.handleScroll);
  },
}
</script>
<style></style>