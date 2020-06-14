<template>
  <v-card>
    <v-card-title class="headline">
      <h1 v-if="error.statusCode === 404">{{ pageNotFound }}</h1>
      <h1 v-else>{{ otherError }}</h1>
    </v-card-title>
    <NuxtLink to="/">Home page</NuxtLink>
    <v-card-actions>
      <v-spacer />
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  layout: 'empty',
  props: {
    error: {
      type: Object,
      default: null
    }
  },
  data() {
    return {
      pageNotFound: '404 Not Found',
      otherError: 'An error occurred'
    }
  },
  head() {
    const title =
      this.error.statusCode === 404 ? this.pageNotFound : this.otherError
    return {
      title
    }
  }
}
</script>

<style type="scss" scoped>
.v-card {
  margin: auto;
}
h1 {
  font-size: 20px;
}
a {
  display: block;
  max-width: fit-content;
  margin: auto;
}
</style>
