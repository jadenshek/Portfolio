<template>
  <div id="WelcomeContainer">
    <img
      class="backgroundImage"
      :src="backgroundImg"
      alt="Background Image appears here"
    />
    <WelcomeText />
  </div>
</template>
<script>
import WelcomeText from "./WelcomeText/WelcomeText.vue";

let svgPath = require(`@/assets/SVGs/HTML.svg`);
let backgroundImg = require(`@/assets/images/WelcomeBackground.png`);
export default {
  name: "WelcomeContainer",
  components: {
    WelcomeText,
  },
  data() {
    return {
      svgPath: svgPath,
      backgroundImg: backgroundImg,
    };
  },
};
</script>
<style>
#WelcomeContainer {
  min-height: min(48rem, 85svh);
  padding: 4rem 1.5rem;
  background-size: cover;
  width: 100%;
  overflow: hidden;
  display: flex;
  justify-content: center;
  object-fit: cover;
  position: relative;
}

.backgroundImage {
  object-fit: cover;
  opacity: 0.6;
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
