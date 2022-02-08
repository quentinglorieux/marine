<template>
<div> 
<div v-for="item in myJson" v-bind:key="item">
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
                  myJson: json
              }
          }
      }
</script>
