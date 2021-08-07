<template>
  <v-app>
    <v-app-bar
      fixed
      app
      flat
    >
      <v-toolbar-title v-text="country ? country.data.name : title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  name: 'DefaultLayout',
  data() {
    return {
      title: 'Datos de Países',
    }
  },
    computed: {
    // Get user from store
    ...mapGetters({
      country: 'country/country',
    }),
  },
}
</script>
