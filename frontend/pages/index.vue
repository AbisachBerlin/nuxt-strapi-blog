<template>
  <v-row>
    <v-col cols="12" sm="6" v-for="post in posts" :key="post.id">
      <BlogCard :post="post" />
    </v-col>
  </v-row>
</template>

<script>
import BlogCard from "~/components/BlogCard.vue";

export default {
  components: {
    BlogCard
  },
  data() {
    return {
      posts: []
    };
  },
  async mounted() {
    let response = await this.$axios.get("posts");
    this.posts = response.data;
  }
};
</script>