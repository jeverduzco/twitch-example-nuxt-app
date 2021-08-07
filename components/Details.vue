<template>
  <v-card v-if="country">
    <v-img
      class="white--text align-end"
      :src="country.data.flag"
    >
      <v-card-title>{{ country.data.nativeName }}</v-card-title>
    </v-img>
    <v-card-text>
      <v-list three-line>
        <v-subheader class="overline">
          Datos del País
        </v-subheader>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Nombre nativo</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.nativeName }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Nombre en inglés</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.name }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Código</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.alpha2Code }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Código de teléfono</v-list-item-title>
            <v-list-item-subtitle> +{{ country.data.callingCodes[0] }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Capital</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.capital }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Moneda principal</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.currencies[0].name }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Idioma principal</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.languages[0].name }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
        <v-divider />
        <v-list-item>
          <v-list-item-content>
            <v-list-item-title>Región</v-list-item-title>
            <v-list-item-subtitle> {{ country.data.region }} </v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-card-text>
    <v-divider />
    <v-card-actions>
      <v-spacer />
      <v-btn
        color="primary"
        nuxt
        text
        block
        to="/"
      >
        Regresar
      </v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  name: 'DetailsComponent',
  props: {
    country: {
      type: Object,
      required: true,
    },
  },
  created() {
    this.$store.commit('country/setCountry', this.country)
  },
  destroyed() {
    this.$store.commit('country/setCountry', null)
  },
}
</script>
<style lang="css" scoped>
.v-card__title {
  background: rgb(0 0 0 / 59%);
}
</style>