<template>
<div > 
    <!-- <PublicationFilter /> -->
    <div  class="flex justify-center gap-5 mt-5 mb-10 text-gray-200 text-xl">
        <button class="button-filter" v-on:click="selectTag('all')" >
          All
        </button> 
    <div v-for="tagItem in tagList" v-bind:key="tagItem.id">
       /  <button v-on:click="selectTag(tagItem.id)" class="button-filter">
          {{tagItem.label}}
        </button> 
    </div>
    </div>
    
<div v-for="item in filteredPubli" v-bind:key="item">
    <PublicationItem
    v-bind:publication="item" >
    </PublicationItem>  </div>

</div>
  
</template>


<script>
      import json from '~/assets/publication.json'
      export default{
          data(){
              return{
                  PubliJson: json,
                  selectedCategory: 'all',
                  tagList: [
                      { id: 397, label: 'Consciousness'},
                      { id: 876, label: 'Eye movement'},
                      { id: 875, label: 'Oscillations Connectivity and Plasticity'},
                      { id: 448, label: 'Neuroaesthetics'},
                      //{ id: 'all', label: 'All'}
                  ]
              }
          },
	
    methods:{  
        selectTag(tagItem) {
            this.selectedCategory = tagItem
        }
    },
    
    computed: {
		filteredPubli: function() {
			var vm = this;
			var tags = vm.selectedCategory;
			
			if(tags === "all") {
				return vm.PubliJson.sort((a, b) => { return b.acf.publication_dop - a.acf.publication_dop;});
			} else {
				return vm.PubliJson.filter(function(publi) {
					 return publi.publication_tags[0] == tags; // == because not the same type
				});
			}
		}
	}
}
</script>

<style lang="postcss" scoped>
.container {
	padding: 20px;
	width: 100%;
	margin: 0 auto;
}
.button-filter {
  @apply bg-transparent focus:text-emerald-400  text-gray-200 hover:text-gray-400 py-2 px-4 text-base;   /* since v3 */
}
</style>

