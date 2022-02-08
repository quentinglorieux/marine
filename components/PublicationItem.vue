<template>
<div>
    <div  class="flex flex-col m-10 ml-40 text-gray-400 hover:scale-105 ease-in duration-200">

        <div class="text-base text-gray-100 "> {{ publication.acf.publication_title }} </div>
        <span> {{ publication.acf.publication_authors }} &nbsp;</span>
        <div class="flex">
            <span class="underline decoration-solid"> {{ publication.acf.publication_journal }}  </span>
            &nbsp; <strong>{{ publication.acf.publication_volume }}</strong> 
            <span v-show="publication.acf.publication_pages" >, {{ publication.acf.publication_pages }} </span>
            &nbsp; ({{ publication.acf.publication_dop }})
        </div>
    </div>
</div>
</template>

<script>
export default {
  props: {
      publication:'',
  },
}
</script>

