<template>
  <div class="p-4">
    <div class="max-w-sm rounded overflow-hidden shadow-lg mb-4">
      <div class="px-6 py-4 pb-2">
        <div class="font-bold text-xl mb-2 text-center">The Coldest Sunset</div>
        <p
          class="text-gray-300 text-base"
        >Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.</p>
      </div>
      <div class="px-6 py-4">
        <span class="badge mr-2">#photography</span>
        <span class="badge mr-2">#travel</span>
        <span class="badge">#winter</span>
      </div>
    </div>
  <div class="bg-midnight text-tahiti">Hello</div>
  </div>

</template>

<style lang="postcss" scoped>
.badge {
  @apply inline-block bg-gray-300 rounded-full px-3 py-1 text-sm font-semibold text-gray-800;
  &:hover {
    @apply bg-gray-50;
  }
}
</style>

<script>
export default {
  name: 'NuxtTutorial'
}
</script>
