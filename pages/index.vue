<script setup>
const story = await useStoryblok("home", {
  // version: "draft",
  version: useRoute().query._storyblok ? "draft" : "published",
  resolve_relations: "featuredProjects.projects",
});
</script>

<template>
  <StoryblokComponent v-if="story" :blok="story.content"></StoryblokComponent>
  <!-- <pre>{{ story.content }}</pre> -->
</template>
