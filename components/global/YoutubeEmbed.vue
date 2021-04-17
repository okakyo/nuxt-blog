<template>
  <div class="youtube">
    <iframe
      :src="`https://www.youtube.com/embed/${vid}`"
      frameborder="0"
      allow="accelerometer; 
                autoplay; 
                encrypted-media; 
                gyroscope; 
                picture-in-picture"
      allowfullscreen
    >
    </iframe>
  </div>
</template>

<script>
export default {
  props: {
    vid: {
      type: String,
      required: true,
      default: '',
    },
  },
}
</script>

<style>
.youtube {
  position: relative;
  padding-bottom: 56.25%;
  height: 0;
  overflow: hidden;
}
.youtube iframe {
  position: absolute;
  top: 0;
  left: 0;
  max-width: 100%;
  width: 600px;
  height: 80%;
}
</style>
