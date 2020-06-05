<template>
  <v-app id="app">
    <Header />
    <v-content>
      <v-container fluid>
        <v-row>
          <v-col cols="12" md="8">
            <nuxt />
          </v-col>
          <v-col cols="12" md="4">
            <Sidebar />
          </v-col>
        </v-row>
      </v-container>
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import Header from "~/components/Header.vue";
import Footer from "~/components/Footer.vue";
import Sidebar from "~/components/Sidebar.vue";

export default {
  components: {
    Header,
    Footer,
    Sidebar
  }
};
</script>

<style lang="scss">
#app {
  background: #f5f5f5;
}
</style>