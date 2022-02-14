<template>
    <nav class="flex justify-center shadow-xs text-ml my-24 inline-block nuxt-link text-gray-500">
        <div>
            <NuxtLink class="button-nav" to="/">Home</NuxtLink> 
        </div>
        <div v-for="item in selected_list" v-bind:key="item.id"  >
            <NuxtLink class="button-nav" :to="item.url">{{item.label}} </NuxtLink> 
      </div>  
    </nav>
</template>


<script>
export default {
    data() {
        return{
            menuList: [
                { id: 1, label: 'Research'},
                { id: 2, label: 'Team'},
                { id: 3, label: 'Publications'},
                { id: 4, label: 'Join us'},
            ]
        }
    },
    computed:{
        selected_list() {
        return this.menuList.map( function(element) {
          return {id : element.id, label : element.label, url : element.label.replace(/\s+/g, '-').toLowerCase()};  //   to camel-case
        })
      },
}
}
</script>



<style lang="postcss" scoped>
nav a:hover{
  color: var(--light);
  }
nav a{
  color: var(--color-gray-500);   /* you need a tailwind plugin to reference tailwind color names */
}

/* The notation  focus:text-[color:var(--secondary)] here is a bit dumb 
since var(--secondary) is defined as a tailwind color in main.css, 
but it might be useful (in the future) to access value in main.css within a tailwind command*/

/* also the @apply notation is used do defined tailwind class in the <style> section 
to avoid lengthy and redundant in the <template>. It requires lang="postcss"   */
.button-nav {
  @apply focus:bg-transparent py-3 px-6 border-2 border-gray-500 focus:border-[color:var(--secondary)] focus:text-[color:var(--secondary)] hover:border-gray-100 ;   /* since v3 */
  border-left:none;
  border-right:none;
}
</style>