  <template>
  <div>
    <h1>Data fetched using fetch</h1>
    <ul>
      <li v-for="mountain in mountains" :key="mountain.title">
        <NuxtLink
          :to="{ name: 'mountains-slug', params: { slug: mountain.slug } }"
        >
          {{ mountain.title }}
        </NuxtLink>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
      data: () => ({
    mountains: []
  }),
  async fetch() {
    this.mountains = await this.$http.$get('https://api.nuxtjs.dev/mountains')
  },
}
</script>
