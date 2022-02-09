<template>
  <p v-if="$fetchState.pending">Fetching mountains...</p>
  <p v-else-if="$fetchState.error">An error occurred :(</p>
  <div v-else>
    <h1>Nuxt Mountains</h1>
    <!-- <ul>
      <li v-for="mountain of mountains" v-bind:key="mountain.slug">{{ mountain.title }}</li>
    </ul> -->
    <h1>Options : {{ options.acf.contactinfo_lab_city }}</h1>
  </div>

</template>

<script>
  export default {
    data() {
      return {
        options: []
      }
    },
    async fetch() {
      // This could also be an action dispatch
      this.options = await fetch(
        'http://marinevernet.fr/wp-json/acf/v3/options/options'
      ).then(res => res.json())
    }
  }
</script>