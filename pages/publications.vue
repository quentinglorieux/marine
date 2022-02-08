<template>
<div> 
    <!-- <PublicationFilter /> -->
	<div class="flex justify-center gap-5">
		<!-- <label><input type="radio" v-model="selectedCategory" value="All" /> All </label>
		<label><input type="radio" v-model="selectedCategory" value="875" /> Oscillations Connectivity and Plasticity</label>
		<label><input type="radio" v-model="selectedCategory" value="876" /> Eye movement</label>
        <label><input type="radio" v-model="selectedCategory" value="397" /> Consciousness</label> -->
        <button v-on:click="selectC1()" class="bg-transparent hover:bg-gray-500 text-blue-200 py-2 px-4 border border-gray-500 hover:border-transparent rounded">
         Consciousness
        </button>
         <button v-on:click="selectC2()" class="bg-transparent hover:bg-gray-500 text-blue-200 py-2 px-4 border border-gray-500 hover:border-transparent rounded">
          Eye movement
        </button>
          <button v-on:click="selectC3()" class="bg-transparent hover:bg-gray-500 text-blue-200 py-2 px-4 border border-gray-500 hover:border-transparent rounded">
          Oscillations Connectivity and Plasticity
        </button>
          <button v-on:click="selectC4()" class="bg-transparent hover:bg-gray-500 text-blue-200 py-2 px-4 border border-gray-500 hover:border-transparent rounded">
          Neuroaesthetics
        </button>
        
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
                  selectedCategory: 'All'
              }
          },
        //  the classic technique to order by date //
//         computed : {
//         orderedYears() {
//           return this.PubliJson.sort((a, b) => { return b.acf.publication_dop - a.acf.publication_dop;});
//       }
//   }
	methods:{
        selectC1() {
          this.selectedCategory = '397'
        },
        selectC2() {
          this.selectedCategory = '876'
        },
        selectC3() {
          this.selectedCategory = '875'
        },
        selectC4() {
          this.selectedCategory = '448'
        },
    },
    computed: {
		filteredPubli: function() {
			var vm = this;
			var tags = vm.selectedCategory;
			
			if(tags === "All") {
				return vm.PubliJson.sort((a, b) => { return b.acf.publication_dop - a.acf.publication_dop;});
			} else {
				return vm.PubliJson.filter(function(publi) {
					 return publi.publication_tags[0] == tags;
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
