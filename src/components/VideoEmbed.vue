<template>
  <div v-if="video">
    <iframe
      width="560"
      height="315"
      :src="videoUrl"
      frameborder="0"
      allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture"
      allowfullscreen
    ></iframe>
  </div>
</template>

<script>
export default {
  name: "VideoEmbed",
  props: ["videoUrl"]
};
</script>
