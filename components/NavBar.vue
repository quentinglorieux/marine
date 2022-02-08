<template>
    <nav class="flex justify-center shadow-xs text-xl my-24 gap-x-4 nuxt-link" >
      <NuxtLink to="/">Home</NuxtLink>
      <NuxtLink to="/research">Research</NuxtLink>
      <NuxtLink to="/team">Team</NuxtLink>
      <NuxtLink to="/publications">Publications</NuxtLink>
      <NuxtLink to="/join-us">Join us</NuxtLink>
    </nav>
</template>

<style>
nav a:hover{
  color: var(--secondary);
  text-decoration:  overline;
}
nav a{
  color: var(--light);
  text-decoration:  underline;
}
</style>