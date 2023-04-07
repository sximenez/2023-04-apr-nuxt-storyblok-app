<script setup>
const route = useRoute();

const story = await useStoryblok(`projects/${route.params.slug}`, {
  // version: "draft",
  version: useRoute().query._storyblok ? "draft" : "published",
});
</script>

<template>
  <StoryblokComponent v-if="story" :blok="story.content"></StoryblokComponent>
  <!-- <pre>{{ story.content }}</pre> -->
</template>
