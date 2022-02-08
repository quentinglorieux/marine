<template>
<div>
    <div  class="flex m-10 text-gray-400 ">
        <div>
            <div class=" text-gray-300 shadow-xs text-2xl mb-10"> 
            {{ title }}
            </div>
            {{ content }}
            </div>
            <nuxt-img class=" object-contain w-200 ml-10 saturate-0" :src="image_name" 
            width="200"
            />
    </div>
</div>
</template>

<script>
export default {
  props: {
      title: '',
      content: '',
      image_name: '',
  }
}
</script>

