<template> 
<div>
    <div  class="flex m-10 text-gray-400 ">
        <div>
            <div class=" text-gray-300 shadow-xs text-2xl mb-10"> 
            Welcome to the {{  planet }}
            </div>
            <!-- <div v-html="options.acf.siteinfo_description"> -->
            </div>
            <!-- <p class="mt-3">To explore these questions, we use a combination of methods including psychophysics, eye movements tracking,
            transcranial magnetic stimulation, functional magnetic resonance imaging, 
            electro- and magnetoencephalography.
            </p> -->
            <p v-if="$fetchState.pending">Fetching mountains...</p>
            <p v-else-if="$fetchState.error">An error occurred :(</p>
            
            </div>
            <nuxt-img class="saturate-0 object-contain" src="/Picture_MV_Brain.jpg" 
            width="300"
            />
             -- {{ options }}
    </div>
</div>
</template>


<script>
  export default {
    data() {
      return {
        options: [],
        planet: ''
      }
    },
    async fetch() {
      // This could also be an action dispatch
      this.options = await fetch(
        'http://marinevernet.fr/wp-json/acf/v3/options/options'
      ).then(res => res.json())
    },
    async asyncData() {
        const planet = await fetch(
            'http://marinevernet.fr/wp-json/acf/v3/options/options'
        ).then((res) => {
            if (res.ok) {
            return res.json()
            }
            throw new Error(res.status)
        })
        return { planet }
    },

  }
</script>




