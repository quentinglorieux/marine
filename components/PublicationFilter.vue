<template>
<div class="flex justify-center gap-5">


<button class="bg-transparent hover:bg-gray-500 text-blue-200 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded">
  Topic 1
</button>

<button v-on:click="changeMessage()" class="bg-transparent hover:bg-blue-500 text-blue-200 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded">
  Topic 2 : {{message}}
</button>

</div>
</template>

<script>
export default {
   data() {
        return {
            message: 'Hello World Vue',
        }
   },
  methods: {
      changeMessage() {
          this.message = 'New'
        },
    }
}
</script>

return data