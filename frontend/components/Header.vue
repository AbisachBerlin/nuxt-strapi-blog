<template>
  <v-app-bar app color="teal" dark>
    <v-toolbar-title>
      <nuxt-link class="site-logo" to="/">Nuxt Strapi Blog</nuxt-link>
    </v-toolbar-title>
  </v-app-bar>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.site-logo {
  color: #fff;
  text-decoration: none;
}
</style>