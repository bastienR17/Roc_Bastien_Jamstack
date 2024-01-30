<script lang="ts" setup>
const { findOne } = useStrapi4();
const route = useRoute();

const { data: recipe, pending } = useAsyncData(
    'recipe',
    () => findOne(`recipes/${route.params.slug}`)
)
</script>

<template>
  <div class="container">
    <template v-if="pending">Chargement de la recette...</template>
    <template v-if="recipe">
      <h1>{{ recipe.data.title }}</h1>
      <p>{{ recipe.data.description }}</p>
      <NuxtImg :src="recipe.data.image.url" alt="maké" />
    </template>
  </div>
</template>
