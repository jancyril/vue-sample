<template>
  <div class="country">
    <h2>{{ country?.name?.common }}</h2>
    <!-- <p>Capital: {{ country?.capital[0] }} </p> -->
    <p>Region: {{ country?.region }} </p>
    <p>Subregion: {{ country?.subregion }} </p>
    <p>Population: {{ formatNumber(country?.population) }} </p>
    <p>Flag: {{ country.flag }}</p>
  </div>
</template>

<script>
export default {
  name: 'CountryItem',
  props: {
    country: {
      type: Object,
      required: true
    }
  },
  methods: {
    formatNumber(number) {
      return number.toLocaleString()
    }
  }
}
</script>
