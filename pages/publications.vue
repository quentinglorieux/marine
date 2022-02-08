<template>
<div> 
    <!-- <PublicationFilter /> -->
    <div  class="flex justify-center gap-5 mt-5">
        <button v-on:click="selectTag('all')" class="bg-transparent focus:bg-teal-600 hover:bg-gray-500 text-blue-200 py-2 px-4 border border-blue-500 hover:border-transparent rounded">
          All
        </button>
    <div v-for="tagItem in tagList" v-bind:key="tagItem.id">
        <button v-on:click="selectTag(tagItem.id)" class="focus:bg-teal-600 bg-transparent hover:bg-gray-500 text-blue-200 py-2 px-4 border border-gray-500 hover:border-transparent rounded">
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
        // selectAll() {
        //   this.selectedCategory = 'all'
        // },
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

<style scoped>
.container {
	padding: 20px;
	width: 100%;
	margin: 0 auto;

}
</style>
