<template>
  <div class="countries">
    <h1>{{ headerName }}</h1>
    <CountryItem v-for="country in alphabeticalCountries" :key="country.name.common" :country="country" />
  </div>
</template>

<script>
import axios from 'axios'
import CountryItem from '../components/CountryItem.vue'

export default {
  name: 'CountriesView',
  components: {
    CountryItem
  },
  data() {
    return {
      headerName: 'Countries',
      countries: []
    }
  },
  computed: {
    alphabeticalCountries() {
      return [...this.countries].sort((a, b) => a.name.common.localeCompare(b.name.common))
    }
  },
  mounted() {
    this.getCountries()
  },
  methods: {
    getCountries() {
      axios.get('https://restcountries.com/v3.1/all').then((response) => {
        this.countries = response.data
        // console.log(response.data)
      }).catch((error) => {
        console.log(error)
      })
    }
  }
}
</script>
