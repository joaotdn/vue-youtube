<template>
  <li @click="onVideoSelect">
    <img :src="thumb" :alt="description" :width="width" :height="height" />
    {{ title }}
  </li>
</template>

<script>
export default {
  name: "VideoListItem",
  props: ["video"],
  computed: {
    thumb() {
      return this.video.snippet.thumbnails.default.url;
    },
    title() {
      return this.video.snippet.title;
    },
    description() {
      return this.video.snippet.description;
    },
    width() {
      return this.video.snippet.thumbnails.default.width;
    },
    height() {
      return this.video.snippet.thumbnails.default.height;
    }
  },
  methods: {
    onVideoSelect() {
      this.$emit("videoSelect", this.video);
    }
  }
};
</script>

<style>
ul {
  list-style: none;
}
li {
  cursor: pointer;
}
</style>
