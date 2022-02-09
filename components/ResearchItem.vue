<template>
<div>
    <div  class="flex m-10 text-gray-400">
        <div>
            <div class=" text-gray-300 shadow-xs text-2xl mb-10"> 
            {{ science_object.title }}
            <!-- {{ title }} : if the prop is more specific see ResearchItem2.vue-->
            </div>
            {{ science_object.content }}
            <!-- {{ content }} : if the prop is more specific -->
            </div>
            <nuxt-img class=" object-contain w-200 ml-10 saturate-0" :src="science_object.image_name" 
            width="200"
            />
    </div>
</div>
</template>

<script>
export default {
  props: {
      science_object: '',
  },
// if the prop is more specific see ResearchItem2.vue-->
//     props: {
//       title: '',
//       content: '',
//       image_name: '',
//   }
}
</script>

