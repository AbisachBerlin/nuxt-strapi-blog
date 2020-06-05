<template>
  <v-card>
    <v-card-title>Recent Posts</v-card-title>
    <v-divider />
    <v-list-item-group>
      <v-list-item v-for="post in posts" :key="post.id" :to="post.slug" nuxt>{{post.title}}</v-list-item>
    </v-list-item-group>
  </v-card>
</template>

<script>
export default {
  name: "RecentPosts",
  data() {
    return {
      posts: []
    };
  },
  async mounted() {
    try {
      await this.$axios.get("posts").then(response => {
        this.posts = response.data;
        this.posts.sort(function(a, b) {
          return new Date(b.updated_at) - new Date(a.updated_at);
        });
      });
    } catch (error) {
      console.log(error);
    }
  }
};
</script>

<style>
</style>