<template>
  <v-navigation-drawer color="black" v-model="drawer" app class="position-fixed">
    <v-list dense fixed>
      <center class="mt-16">
        <v-list-item v-for="item in items" :key="item.title" link :exact="item.exact" @click="scroll(item.title)">
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title class="mb-4">{{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </center>
    </v-list>
  </v-navigation-drawer>

  <v-app-bar app color="black" dark fixed style="position: fixed;">
    <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
    <!-- <v-toolbar-title class="ml-4 text-h3" style="font-weight: bold;">Prajwal</v-toolbar-title> -->
    <div class="logo  py-2 px-4">
      <div style="font-size: 2rem;">Mallu</div>
      <pre><div class="subtext ml-1" style="font-size: 0.5rem;">The Photographer <v-icon color="pink">mdi-camera</v-icon></div></pre>
    </div>
    <v-spacer></v-spacer>
    <v-btn class="menu mr-3" @click="scroll(item.title)" text v-for="item in items" :key="item.title" :exact="item.exact">
      {{ item.title }}
    </v-btn>
  </v-app-bar>
</template>

<script>
export default {
  name: 'NavigationMenu',
  data() {
    return {
      drawer: false,
      items: [
        { title: 'home', icon: 'mdi-home', exact: true },
        { title: 'gallery', icon: 'mdi-image' },
        { title: 'about', icon: 'mdi-account' },
        { title: 'services', icon: 'mdi-cogs', exact: true },
        { title: 'testimonials', icon: 'mdi-account' },
        { title: 'contact', icon: 'mdi-phone' }
      ]
    };
  },
  methods: {
    scroll(refName) {
      const element = document.getElementById(refName);
      element.scrollIntoView({ behavior: "smooth" });
    },
  },
};
</script>

<style>
@media screen and (max-width: 600px) {
  .menu {
    visibility: hidden;
  }
}
</style>
