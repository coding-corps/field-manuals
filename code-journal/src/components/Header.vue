<template>
  <v-card class="overflow-hidden">
    <v-app-bar app shrink-on-scroll prominent class="head">
      <router-link to="/">
        <v-img href="/" :src="require('../assets/images/logo-w.svg')"></v-img>
      </router-link>
      <v-spacer></v-spacer>
      <v-btn dark to="/" icon>
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-btn dark to="/about" icon>
        <v-icon>mdi-information-variant</v-icon>
      </v-btn>
      <v-btn dark to="/entries" icon>
        <v-icon>mdi-message-bulleted</v-icon>
      </v-btn>
    </v-app-bar>
  </v-card>
</template>
<script>
export default {
  name: "AppHeader",
  data: () => ({
    icons: ["mdi-facebook", "mdi-twitter", "mdi-linkedin", "mdi-instagram"],
    drawer: false,
    group: null,
  }),
  watch: {
    group() {
      this.drawer = false;
    },
  },
};
</script>
<style>
.head {
  text-align: center !important;
  color: aliceblue !important;
  background-color: #1c1b1bf0 !important;
  margin-bottom: 200px !important;
}
</style>
