<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="8">
      <v-card class="logo py-4 d-flex justify-center">
        <NuxtLogo />
      </v-card>
      <v-card>
        <v-card-title class="headline">
          <h3 class="text-center card-texts">
            Aplicación de Datos de Países
          </h3>
        </v-card-title>
        <v-card-text>
          <p class="text-center card-texts">
            Escribe el nombre en inglés del País del que deseas ver los datos y da clic en consultar.
          </p>
        </v-card-text>
        <Search />
      </v-card>
    </v-col>
  </v-row>
</template>
<script>
export default {
  name: 'SearchPage',
   head() {
    return {
      htmlAttrs: {
        lang: 'es',
        title: 'Datos de Países'
      },
    }
  },
}
</script>
<style scoped>
.card-texts {
  width: 100%;
}
</style>
