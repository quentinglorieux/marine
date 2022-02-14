  <template>
  <div>
    <h1>Data fetched using asyncData</h1>
    <div>
        {{  options.acf.siteinfo_site_tag_line }}
    </div>
    <M2 />
  </div>
</template>

<script>
export default {
  async asyncData({ $http }) {
    const options = await $http.$get('http://marinevernet.fr/wp-json/acf/v3/options/options')
    return { options }
  }
}
</script>

