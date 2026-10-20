<template lang="">
  <div id="pageContainer">
    <PageButton
      buttonText="Previous Page"
      @click="$emit('decrementCurrent')"
      :disabled="isStart"
      :svgPath="leftArrow"
    />
    <PageButton
      buttonText="Next Page"
      @click="$emit('incrementCurrent')"
      :disabled="isEnd"
      :svgPath="rightArrow"
    />
  </div>
</template>
<script>
import PageButton from "./PageButton/PageButton.vue";

let rightArrow = require("@/assets/SVGs/RightArrow.svg");
let leftArrow = require("@/assets/SVGs/LeftArrow.svg");

export default {
  name: "PageContainer",
  components: { PageButton },
  props: {
    currentPage: { type: Number },
    isStart: { type: Boolean },
    isEnd: { type: Boolean },
  },
  data() {
    return {
      rightArrow: rightArrow,
      leftArrow: leftArrow,
    };
  },
};
</script>
<style scoped>
#pageContainer {
  display: flex;
  align-items: center;
  justify-content: space-around;
  gap: 1rem;
  width: 100%;
  margin: 1rem 0 0;
}
</style>
