<template>
  <div>
    <SearchBar @termChange="onTermChange" />
    <VideoDetail :video="videoSelect" />
    <VideoList :videos="videos" @videoSelect="onVideoSelect" />
  </div>
</template>

<script>
import axios from "axios";
import SearchBar from "./components/SearchBar";
import VideoList from "./components/VideoList";
import VideoDetail from "./components/VideoDetail";

const API_KEY = "AIzaSyBN553J19_2PGLJ5SQ951Rx5mHsEYx-Ng4";

export default {
  name: "App",
  components: {
    SearchBar,
    VideoList,
    VideoDetail
  },
  data: function() {
    return {
      videos: [],
      videoSelect: null
    };
  },
  methods: {
    onVideoSelect(video) {
      this.videoSelect = video;
    },
    onTermChange(searchTerm) {
      axios
        .get("https://www.googleapis.com/youtube/v3/search", {
          params: {
            key: API_KEY,
            type: "video",
            part: "snippet",
            q: searchTerm
          }
        })
        .then(res => {
          this.videos = res.data.items;
        });
    }
  }
};
</script>
