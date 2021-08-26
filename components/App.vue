<template>
  <div>
    <p>hello from the App component</p>
    <p>ffmpeg loaded: {{ ready }}</p>
  </div>
</template>

<script lang="ts">
import { createFFmpeg, fetchFile } from "@ffmpeg/ffmpeg";

const ffmpeg = createFFmpeg({ log: true });

export default {
  data() {
    return {
      ready: false,
    };
  },
  methods: {
    async load() {
      console.log('start loading ffmpeg...');
      await ffmpeg.load();
      console.log('finished loading ffmpeg...');
      this.ready = true;
    },
  },
  created() {
    this.load();
  },
};
</script>

<style>
</style>