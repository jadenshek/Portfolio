<template>
  <a :href="href" target="_blank" :title="createToolTip()"
    ><img :src="svgPath" :alt="alt"
  /></a>
</template>
<script>
export default {
  name: "SocialItem",
  props: {
    svgPath: { type: String },
    altText: { type: String },
    href: { type: String },
    title: { type: String },
  },
  methods: {
    createToolTip() {
      return `Click me to visit my ${this.altText} page!`;
    },
  },
  computed: {
    alt() {
      return `${this.altText} Icon`;
    },
  },
};
</script>
<style scoped>
img {
  display: block;
  width: clamp(40px, 12vw, 70px);
  max-width: 100%;
  height: auto;
  margin: auto;
}
</style>
