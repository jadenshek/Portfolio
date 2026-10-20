<template>
  <div class="mediaGraphic">
    <img :src="imagesrc" alt="" />
  </div>
</template>
<script>
export default {
  name: "mediaGraphic",
  props: {
    imagesrc: { type: String },
  },
};
</script>
<style scoped>
.mediaGraphic {
  background-size: cover;
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  object-fit: cover;
  position: relative;
  align-items: center;
  border-radius: 2rem;
}

img {
  display: block;
  width: 100%;
  height: auto;
}
</style>
