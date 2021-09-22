<template>
  <v-app id="inspire">
    <v-app-bar color="white" fixed flat>
      <v-row>
        <v-container class="d-flex">
          <v-toolbar-title class="green--text font-weight-bold">
            ASPIRE CREDIT LENDING</v-toolbar-title
          >
          <v-spacer></v-spacer>
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn class="" text href="#home">Home </v-btn>
            <v-btn class="" text href="#services">Services</v-btn>
            <v-btn class="" text href="#contact">Contact</v-btn>
          </v-toolbar-items>

          <v-menu offset-y>
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                class="hidden-md-and-up"
                color="grey lighten-3"
                depressed
                v-bind="attrs"
                v-on="on"
              >
                <v-icon class="gr"> mdi-menu </v-icon>
              </v-btn>
            </template>
            <v-list>
              <v-list-item v-for="link in links" :key="link.icon">
                <v-list-item-title>{{ link }}</v-list-item-title>
              </v-list-item>
            </v-list>
          </v-menu>
        </v-container>
      </v-row>
    </v-app-bar>

    <v-main class="">
      <v-fade-transition mode="out-in">
        <router-view></router-view>
      </v-fade-transition>
      <snackbar></snackbar>
    </v-main>
  </v-app>
</template>
<script>
import Snackbar from "@/components/Snackbar";
export default {
  name: "App",

  components: {
    Snackbar,
  },

  data: () => ({
    links: ["home", "services", "contact"],
  }),
  methods: {
    menuItems() {
      return this.menu;
    },

    goTo(path) {
      this.$router.push({ path: path });
    },
  },
};
</script>
<style lang="sass">

html
    scroll-behavior: smooth
.height-100
    min-height: 100vh

.about
    background: linear-gradient(to bottom, rgb(0 169 6 / 81%) 0, rgb(2 142 20 / 80%) 100%), url('~@/assets/street.jpg')
    background-size: cover
    background-repeat: no-repeat
    background-position: center

.page-section
    padding: 8rem 0 !important

.divider
    margin:0 auto
    width: 90px
    height: 4px
    background: #fff
    border-radius: 2px
</style>
