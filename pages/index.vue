<template>
<div> 
  <Intro />
  <Adress />
<!-- <div v-for="item in items" v-bind:key="item"><Card1/>  </div> -->
</div>
  
</template>

<script>
export default {
  name: 'IndexPage',
   data() {
  return {
    items: [
      { message: 'Foo' }, 
      ]
  }
}
}
</script>
