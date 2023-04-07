<script setup>
defineProps({ blok: Object });
</script>

<template>
  <div class="container">
    <h1>{{ blok.title }}</h1>
    <div class="featured-projects">
      <!-- <div class="project" v-for="project in blok.projects">
        <NuxtLink>
          <h3>{{ project.name }}</h3>
        </NuxtLink>
      </div> -->
      <div class="project" v-for="project in blok.projects" :key="project._uid">
        <NuxtLink
          :to="{ name: 'projects-slug', params: { slug: project.slug } }"
        >
          <img :src="project.content.image?.filename || 'No image :('" />
          <h3>{{ project.content.name || "No name :(" }}</h3>
          <!-- {{ project }} -->
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
h1 {
  margin-left: 10px;
}
</style>
