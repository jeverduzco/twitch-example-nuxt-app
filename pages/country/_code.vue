<template>
  <v-row justify="center" align="center">
    <v-col v-if="country" cols="12" sm="8" md="8">
      <Details :country="country" />
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: 'DetailsPage',
  data() {
    return {
      country: null,
    }
  },
  async fetch() {
    this.country = await this.$axios.get(
      'https://restcountries.eu/rest/v2/alpha/' + this.$route.params.code
    )
  },
  fetchOnServer: false,
  head() {
    return {
      htmlAttrs: {
        lang: 'es',
        title: 'Detalles del País'
      },
    }
  },
}
</script>