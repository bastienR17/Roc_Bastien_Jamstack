<script lang="ts" setup>
const links = [
  {
    id: 2,
    title: 'Exemple de recherche',
    url: '/exemple-recherche',
  },
]
</script>

<template>
  <nav class="w-full">
    <div class="container">
      <div class="flex items-center space-between w-full">
        <NuxtLink to="/">
          <p>home</p>
        </NuxtLink>
        <ul class="list-none flex gap-4 my-0 ml-auto">
          <li v-for="link in links" :key="link.id">
            <NuxtLink :to="link.url">
              {{ link.title }}
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>
