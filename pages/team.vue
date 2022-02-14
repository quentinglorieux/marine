  <template>
  <div>
      <PI />
    <!-- <ul id="joblist">
      <li v-for="job in jobData" :key="job.id">
        <Jobs :jobData="job" />
        </li>
    </ul> -->
    
    <!-- <M2 /> -->
  </div>
</template>

<script>
export default {
   data() {
      return {
        xpert: '',
      }
    },
  async asyncData({ $http }) {
    const jobData = await $http.$get('http://marinevernet.fr/wp-json/wp/v2/job')
    return { jobData }
  },
  // async fetch() {
  //     // This could also be an action dispatch
  //     this.xpert = await fetch(
  //       'http://marinevernet.fr/wp-json/wp/v2/job'
  //     ).then(res => res.json())
  //   },
}
</script>

