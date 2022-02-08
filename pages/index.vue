<template>
<div> 
<div v-for="item in items" v-bind:key="item"><Card1/>  </div>
</div>
  
</template>

<script>
export default {
  name: 'IndexPage',
   data() {
  return {
    items: [
      { message: 'Foo' }, 
      { message: 'Bar' },
      { message: 'Foo' }, 
      { message: 'Bar' },
      ]
  }
}
}
</script>
