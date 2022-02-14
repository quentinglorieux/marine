<template> 
<div>
    <div  class="flex m-10 text-gray-400 ">
        <div>
            <div class=" text-gray-300 shadow-xs text-2xl mb-10"> 
            {{  memberData[4].acf.member_first_name }} {{memberData[4].acf.member_last_name}}, PhD

            </div>
            <div class="mr-10 mb-10" v-html=" memberData[4].acf.member_short_description"> </div>
           
            <div class="mr-10 hover:text-green-400">
                <a :href="memberData[4].acf.member_cv">
                    Download my CV 
                </a>
            </div>
            <!-- <p v-if="$fetchState.pending">Fetching mountains...</p>
            <p v-else-if="$fetchState.error">An error occurred :(</p> -->
            
            </div>
            <img class="object-contain saturate00" :src="memberData[4].acf.member_picture.url" width="300">
            <!-- <nuxt-img class="object-contain saturate00" :src="memberData[4].acf.member_picture.url" 
            width="300"
            /> -->
    </div>
</div>
</template>

<style> 
.saturate00{
 -webkit-filter  : saturate(0%); 
 filter    : saturate(0%); 
}
/* also usable in ResearchItem.vue */
</style>

<script>
  export default {
    data() {
      return {
        memberData: '',
       // planet: {}
      }
    },
    async fetch() {
      // This could also be an action dispatch
      this.memberData = await fetch(
        'https://marinevernet.fr/wp-json/acf/v3/member'
      ).then(res => res.json())
    },
    // async asyncData() {
    //     const planet = await fetch(
    //         'http://marinevernet.fr/wp-json/acf/v3/options/options'
    //     ).then((res) => {
    //         if (res.ok) {
    //         return res.json()
    //         }
    //         throw new Error(res.status)
    //     })
    //     return { planet }
    // },

  }
</script>




