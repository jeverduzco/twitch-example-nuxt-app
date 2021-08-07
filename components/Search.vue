<template>
  <div>
    <v-col cols="12">
      <v-autocomplete
        v-model="selected"
        :items="coutries.data"
        return-object
        no-data-text="No hay datos"
        label="Busca un País"
        item-text="name"
      />
    </v-col>
    <v-divider />
    <v-card-actions>
      <v-spacer />
      <v-btn
        color="primary"
        nuxt
        text
        block
        :to="selected ? '/country/' + selected.alpha2Code : ''"
        :disabled="!selected"
      >
        Consultar
      </v-btn>
    </v-card-actions>
  </div>
</template>
<script>
export default {
  name: 'SearchComponent',
  data() {
    return {
      coutries: [],
      selected: null,
    }
  },
  async fetch() {
    this.coutries = await this.$axios.get(
      'https://restcountries.eu/rest/v2/all'
    )
  },
  fetchOnServer: false,
}
</script>