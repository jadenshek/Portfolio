<template>
  <div class="aboutImage"><img :src="src" alt="" /></div>
</template>

<script>
export default {
  name: "AboutImage",
  props: {
    src: {
      type: String,
    },
  },
};
</script>

<style scoped>
.aboutImage {
  overflow: hidden;
  width: 100%;
  border-radius: 63px;
  background-size: cover;
}
img {
  display: block;
  width: 100%;
  height: auto;
  margin: 0;
}
</style>
