<template>
<div class="flex flex-col text-gray-300 content-end my-20 mr-10 text-right">
    <div > {{address.ligne1}}, </div>
    <div > {{address.ligne2}}. </div>
    <div > {{options.acf.contactinfo_lab_zip}} {{options.acf.contactinfo_lab_city}} </div>
    <div > {{options.acf.contactinfo_email}}</div>
</div>
</template>



<script>
  export default {
    data() {
      return {
        address: {
          ligne1: 'CRNL, Impact Team, Bat. Inserm',
          ligne2: '16 Avenue du Doyen Jean Lépine'
        },
        options: '',
      }
    },
    async fetch() {
      // This could also be an action dispatch
      this.options = await fetch(
        'http://marinevernet.fr/wp-json/acf/v3/options/options'
      ).then(res => res.json())
    },

  }
</script>


<style scoped>
p span {
  display: block;
}

</style>> 
