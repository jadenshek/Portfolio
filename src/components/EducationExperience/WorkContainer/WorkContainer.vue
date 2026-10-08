<template lang="">
  <div id="experience" @resize="updatePageSize">
    <h4>Experience</h4>
    <WorkItem v-for="page in paginated()" :key="page" v-bind="page" />
    <PageContainer
      :currentPage="current"
      @incrementCurrent="current++"
      @decrementCurrent="current--"
      :isStart="isStart"
      :isEnd="isEnd"
    />
  </div>
</template>
<script>
import WorkItem from "../WorkItem/WorkItem.vue";
import PageContainer from "../../Utility/Pagination/PageContainer.vue";

let experience = require("@/assets/api/experience.json");

function compareYear(first, second) {
  const firstIsPresent = first.endYear === "Present";
  const secondIsPresent = second.endYear === "Present";

  if (firstIsPresent !== secondIsPresent) {
    return firstIsPresent ? -1 : 1;
  }

  if (!firstIsPresent && first.endYear !== second.endYear) {
    return Number(second.endYear) - Number(first.endYear);
  }

  return Number(second.startYear) - Number(first.startYear);
}

experience.sort(compareYear);

export default {
  name: "WorkContainer",
  components: { WorkItem, PageContainer },
  computed: {
    indexStart() {
      return (this.current - 1) * this.pageSize;
    },
    indexEnd() {
      return this.indexStart + this.pageSize;
    },
    isStart() {
      return this.current - 1 === 0;
    },
    isEnd() {
      return (
        this.current >= Math.ceil(this.experienceList.length / this.pageSize)
      );
    },
    pageSize() {
      if (
        (this.windowWidth > 1500) |
        (this.windowWidth > 600 && this.windowWidth < 1024)
      ) {
        return 3;
      }
      return 2;
    },
  },
  methods: {
    paginated() {
      return this.experienceList.slice(this.indexStart, this.indexEnd);
    },
    onScreenResize() {
      window.addEventListener("resize", () => {
        this.updateScreenWidth();
      });
    },
    updateScreenWidth() {
      this.windowWidth = window.innerWidth;
    },
  },
  data() {
    return {
      current: 1,
      experienceList: experience,
      windowWidth: 0,
    };
  },
  mounted() {
    this.updateScreenWidth();
    this.onScreenResize();
  },
};
</script>
<style scoped>
#experience {
  display: flex;
  flex-direction: column;
  flex-grow: 1;
  min-width: 0;
  width: 100%;
  align-self: flex-start;
}
</style>
