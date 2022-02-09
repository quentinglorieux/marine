<template>
<div >
    <div  class="flex flex-col m-5 text-gray-400 hover:scale-105 fade-in-text ease-in duration-200">

        <div class="text-base text-gray-100 "> {{ publication.acf.publication_title }} </div>
        <span> {{ publication.acf.publication_authors }} &nbsp;</span>
        <div class="flex">
            <a :href="publication.acf.publication_doi" class="underline decoration-solid hover:text-gray-200 "> {{ publication.acf.publication_journal }}  </a>
            &nbsp; <strong>{{ publication.acf.publication_volume }}</strong> 
            <span v-show="publication.acf.publication_pages.length >1" >, {{ publication.acf.publication_pages }} &nbsp; </span>
            <span> ({{ publication.acf.publication_dop }}) </span>
        </div>
        
    </div>
    <hr class="flex flex-col ml-5 mb-2 separateur" />
</div>
</template>

<script>
export default {
  props: {
      publication:'',
  },
}
</script>

<style scoped>
.separateur{
    height: 1px;
    border-width: 1px;
    border-color: var(--color-gray-500);
    width: 60%;
}

/* Animation */
.fade-in-text {
  display: inline-block;
  animation: fadeIn linear 0.4s;
  -webkit-animation: fadeIn linear 0.4s;
  -moz-animation: fadeIn linear 0.4s;
  -o-animation: fadeIn linear 0.4s;
  -ms-animation: fadeIn linear 0.4s;
}

@keyframes fadeIn {
  0% {opacity:0;}
  100% {opacity:1;}
}

@-moz-keyframes fadeIn {
  0% {opacity:0;}
  100% {opacity:1;}
}

@-webkit-keyframes fadeIn {
  0% {opacity:0;}
  100% {opacity:1;}
}

@-o-keyframes fadeIn {
  0% {opacity:0;}
  100% {opacity:1;}
}

@-ms-keyframes fadeIn {
  0% {opacity:0;}
  100% {opacity:1;}
}


</style>