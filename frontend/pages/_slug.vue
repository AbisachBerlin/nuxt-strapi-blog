<template>
  <v-container v-if="post.title">
    <h1>{{post.title}}</h1>
    <v-img class="mt-5 mb-5" max-height="300" :src="backendUrl + post.image.url"></v-img>
    <article v-html="$md.render(post.content)"></article>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      post: {},
      backendUrl: process.env.strapiBaseUri
    };
  },

  async mounted() {
    try {
      await this.$axios
        .get("posts?slug=" + this.$route.params.slug)
        .then(response => {
          this.post = response.data[0];
        });
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style>
</style>