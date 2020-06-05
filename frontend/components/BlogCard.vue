<template>
  <v-card :to="post.slug" nuxt>
    <v-img :src="backendUrl + post.image.url"></v-img>

    <v-card-title>{{post.title}}</v-card-title>

    <v-card-subtitle>{{post.content.substring(0, 100) + '...'}}</v-card-subtitle>
  </v-card>
</template>

<script>
export default {
  name: "BlogCard",
  props: ["post"],
  data() {
    return {
      backendUrl: process.env.strapiBaseUri
    };
  }
};
</script>