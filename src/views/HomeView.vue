<template>
  <v-app id="home">
    <NavigationMenu />
    <v-main>
      <section id="home">
        <v-carousel cycle height="600"  hide-delimiter-background show-arrows="hover">
          <v-carousel-item v-for="(image, i) in images" :key="i" :src="image.src" cover>
            <div class="d-flex fill-height justify-center align-center text-center">
              <div>
                <span class="text-h2 font-weight-bold" :style="{ color: colors[i] }"> {{ slides[i] }} </span>
                <p class="text-center text-sm-h6" style="color: rgb(255, 255, 255);">{{ pyara[i] }}</p>
              </div>
            </div>
          </v-carousel-item>
        </v-carousel>
      </section>

      <section class="bg-black" id="gallery">
        <h1 class="text-h4 px-8 py-6 text-decoration-overline text-white font-bold">Our Work</h1>
        <v-container>
          <div class="d-flex bg-white">
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background6.jpg"></v-img>
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background2.jpg"></v-img>
          </div>
          <div class="d-flex flex-row mb-6 bg-white">
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background8.jpg"></v-img>
            <v-img class="ma-2 pa-5" style="width: 4%;" src="@/assets/background.jpg"></v-img>
          </div>
        </v-container>
        <br>
        <br>
      </section>
      <v-container id="about">
        <h1 class="text-h4 mb-6 text-center pt-15 text-decoration-overline font-bold">About Us</h1>
        <div class="flex justify-center">
          <div class="w-2/3">
            <p class="text-h7 pl-16 pr-16 pb-16 text-center"
              style="line-height: 2.4rem; letter-spacing: 0.08rem; word-spacing: 0.09rem; text-align: center;">
              <span class="text-decoration-underline">Mallu The Photographer</span> is a Gadag-based photography business
              that specializes in capturing the essence of life's
              most
              precious moments.
              Our team of talented photographers is dedicated to providing you with high-quality, stunning images that
              will
              last a lifetime.
              <br>
              Whether you're looking for a wedding photographer or simply need a portrait session,
              Mallikarjun has the expertise and experience to deliver exceptional results.
              We pride ourselves on our attention to detail and commitment to customer satisfaction,
              and we strive to exceed your expectations with every shoot.
              Contact us today to learn more about our services and to schedule your session.
            </p>
          </div>
        </div>
      </v-container>
      <section style="background-color:rgb(240, 240, 240);" id="services">
        <h1 class="text-h4 mb-6 text-center pt-15 text-decoration-overline" style="font-weight: bold;">Our Services</h1>
        <div class="d-flex flex-wrap ma-10 justify-center">
          <div v-for="card in cards" :key="card.id" class="pa-10">
            <va-card stripe :stripe-color=card.color textColor="#424242" style="width: 18rem;">
              <va-card-title text-color="#000000" class="text-h6 justify-center">{{ card.title }}</va-card-title>
              <va-image :src="card.imageSrc" style="width: 100%; height: 20rem;">
                <va-card-title text-color="#fff">{{ card.title }}</va-card-title>
              </va-image>
              <va-card-content style="line-height: 1.5rem">{{ card.content }}</va-card-content>
            </va-card>
          </div>
        </div>
        <center> <v-btn color="black" class="mb-15"> And More...</v-btn></center>
      </section><br>
      <section id="testimonials" class="mt-10">
        <center class="text-h4 text-center text-decoration-overline pb-10">Testimonials</center>
        <v-carousel cycle hide-delimiter-background height="550" delimiter-icon="mdi-heart"
          style="background-color: gainsboro;">
          <v-carousel-item v-for="(item, index) in testimonials" :key="index">
            <div class="d-flex fill-height justify-center align-center text-center ml-16 mr-16">
              <div>
                <v-avatar class="mb-5" size="80" style="border: 1px solid rgb(72, 71, 71);">
                  <v-img :src="item.src" alt="Prajwal" cover></v-img>
                </v-avatar><br>
                <span class=" text-h6 font-weight-bold" :style="{ color: colors[i] }"> {{ item.text }} </span>
                <p class="text-center text-sm-h6 mt-5">{{ item.author }}</p>
              </div>
            </div>
          </v-carousel-item>
        </v-carousel>
      </section>
      <LocationPage />
      <section style="background-color:rgb(240, 240, 240)" id="contact">
        <v-container class="py-8 lg:py-12 xl:py-16">
          <h1 class="text-center text-decoration-overline text-h4 pt-5">Contact Us</h1>
          <v-row class="flex-wrap flex-row-reverse mt-10 mb-10">
            <v-col cols="12" md="6" class="mt-10">
              <div class="rich-text-block">
                <h3 class="mb-3" style="font-size: 1.7rem; font-weight: lighter;">Get in Touch with Us</h3>
                <p style="font-size: 1.3rem; letter-spacing: 0.09rem; line-height: 2rem; color: #484848;">Have a
                  question or
                  interested in our photography services? Fill out the form below
                  and we'll get back to you as soon as possible. We can't wait to hear from you!</p>
              </div>
            </v-col>

            <v-col cols="12" sm="6">
              <v-form>
                <v-container>
                  <v-row>
                    <v-col cols="12" sm="6" md="6">
                      <v-text-field label="Name" v-model="name" placeholder="Enter Your Name"
                        variant="outlined"></v-text-field>
                    </v-col>

                    <v-col cols="12" sm="6" md="6">
                      <v-text-field label="Email" v-model="email" placeholder="Enter Your Email"
                        variant="outlined"></v-text-field>
                    </v-col>

                    <v-col cols="12" sm="12" md="16">
                      <v-textarea label="Message" v-model="message" auto-grow variant="outlined" rows="5" row-height="25"
                        shaped placeholder="Write Your Message..."></v-textarea>

                    </v-col>
                    <v-row class="mr-3">
                      <v-btn class="ml-auto send" color="black" rounded="l" @click="submit()">Send</v-btn>
                    </v-row>
                  </v-row>
                </v-container>
              </v-form>
            </v-col>
          </v-row>
          <v-dialog v-model="dialog" transition="dialog-top-transition" width="350" height="250">
            <v-card>
              <v-toolbar :color="dialogColor" :title="dialogTitle"></v-toolbar>
            </v-card>
          </v-dialog>
        </v-container>
        <FooterPage />
      </section>
    </v-main>
  </v-app>
</template>

<script>
import { defineComponent } from 'vue';
import NavigationMenu from '@/components/NavigationMenu.vue';
import LocationPage from '@/components/LocationPage.vue'
import FooterPage from '@/components/FooterPage.vue';

export default defineComponent({
  name: 'HomeView',
  components: {
    NavigationMenu,
    LocationPage,
    FooterPage,
  },
  data: () => ({
    name: '',
    email: '',
    message: '',
    dialog: false,
    dialogTitle: '',
    dialogColor: '',
    cards: [
      {
        id: 1,
        imageSrc: require("../assets/s1.jpg"),
        color: '#2196F3',
        title: 'Product Photography',
        content: "We capture high-quality images of your products that not only showcase their features but also entice customers to make a purchase."
      },
      {
        id: 2,
        imageSrc: require("../assets/av.jpg"),
        title: 'Event Photography',
        color: '#E91E63',
        content: 'Whether its a corporate event or a wedding, our photographers will capture every moment, and delivering stunning images that tell your story.',
      },
      {
        id: 3,
        imageSrc: require("../assets/s3.jpg"),
        title: 'Portrait Photography',
        color: '#FFEA00',
        content: 'We create timeless portraits that capture your personality and convey your message. Our photographers work with you to create a unique visual narrative.',
      },
    ],
    testimonials: [
      {
        text: "Mallu's photography skills are exceptional! The attention to detail and creativity in each shot is truly impressive. I highly recommend him for any photography needs in Bengaluru. Thank you for capturing such beautiful memories!",
        author: "- Vijay",
        src: require("../assets/t8.jpg"),
      },
      {
        text: "Mallu's photography skills are top-notch! He captured the essence of my event beautifully. He was professional, punctual, and his attention to detail was impressive. Thank you for making my special day even more memorable with your stunning photographs.",
        author: "- Madhu",
        src: require("../assets/t1.jpg"),
      },
      {
        text: "mallu is an amazing photographer! His attention to detail and creativity are unparalleled. He captured the essence of my event perfectly and delivered the photos promptly. Highly recommend his services to anyone looking for beautiful photos!",
        author: "- Kiran",
        src: require("../assets/t9.jpg"),
      },
      {
        text: "I had an incredible experience with Mallu Photography! Their attention to detail and creativity truly captured the essence of my special moments. The team was professional, friendly. Thank you for the stunning photographs that I will cherish forever!",
        author: "- Prashanth",
        src: require("../assets/t6.jpg"),
      },      {
        text: "Mallu's photography skills are truly exceptional. They captured the essence of our event beautifully and the pictures turned out to be stunning. Thank you for making our memories last a lifetime!",
        author: "- Nanda",
        src: require("../assets/t4.jpg"),
      },
    ],
    images: [
      { src: require("../assets/home1.jpg") },
      { src: require("../assets/home4.jpeg") },
      { src: require("../assets/home3.jpeg") },
      { src: require("../assets/home5.jpeg") },
      { src: require("../assets/home7.jpeg") },
    ],
    slides: ["Capture Life's Moments Beautifully",
      'Capture Memories That Last Forever',
      'Capture Your Memories Today',
      'Unforgettable Moments, Captured!',
      'Capture Memorable Moments'],
    pyara: [
      "Experience the art of photography with Mallu's professional services. Perfect for weddings, corporate events, family portraits, landscapes, and more!",
      "Let us help you create beautiful memories with our professional photography services. Book now!",
      "Let us turn your special moments into timeless photographs. Book a session with us now!",
      "Our professional photography services are here to help you create beautiful memories that last a lifetime. Book now and let us capture the magic!",
      "Professional photography services to preserve your special occasions and create lasting memories."
    ],
    colors: [
      'rgb(0, 0, 0)',
      '#FFFF00',
      '#EC407A',
      'rgb(255, 165, 0)',
      'rgb(128, 0, 128)',
    ],
    testi: [
      { src: require("../assets/t4.jpg") },
      { src: require("../assets/t1.jpg") },
      { src: require("../assets/t2.jpg") },
      { src: require("../assets/t4.jpg") },
      { src: require("../assets/t4.jpg") },

    ]
  }),
  methods: {
    submit() {
      if (this.name && this.email && this.message) {
        this.dialogTitle = 'Message sent successfully...!';
        this.dialogColor = 'green';
        this.name = '';
        this.email = '';
        this.message = '';
      } else {
        this.dialogTitle = 'Enter required fields...!';
        this.dialogColor = 'red';
      }
      this.dialog = true;
    }
  }
});
</script>