<script setup>
defineProps({ blok: Object });
</script>

<template>
  <div class="container project-page">
    <div class="project-title">
      <h1>{{ blok.name || "Project name here" }}</h1>
      <NuxtLink :to="{ name: 'index' }">Go Back</NuxtLink>
    </div>

    <div class="project-description">
      <img
        :src="
          blok.image?.filename ||
          'https://images.pexels.com/photos/1142950/pexels-photo-1142950.jpeg?auto=compress&cs=tinysrgb&w=600'
        "
        :alt="blok.image?.alt"
      />
      <p>{{ blok.description || "Description here" }}</p>
    </div>
  </div>
</template>
