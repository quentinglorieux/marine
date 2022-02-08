<template>
<div>
    <div  class="flex m-10 text-gray-400 ">

            <div class=" text-gray-300 shadow-xs text-2xl mb-10"> 
            {{ publication.acf.publication_title }}
            </div>
            <div>
            {{ publication.acf.publication_journal }} -   {{ publication.acf.publication_dop }}
            </div>
    </div>
</div>
</template>

<script>
export default {
  props: {
      publication:'',
  }
}
</script>

