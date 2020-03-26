<template>
  <div v-if="video">
    <h4>{{ video.snippet.title }}</h4>
    <iframe :src="videoUrl"></iframe>
    <p>{{ video.snippet.description }}</p>
  </div>
</template>

<script>
export default {
  name: "VideoDetail",
  props: ["video"],
  computed: {
    videoUrl() {
      const { videoId } = this.video.id;
      return `https//youtube.com/embed/${videoId}`;
    }
  }
};
</script>
