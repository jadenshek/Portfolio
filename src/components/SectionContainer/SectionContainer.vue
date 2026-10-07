<template>
  <div>
    <section v-if="!alignedRight" class="section">
      <div class="content">
        <slot name="content" />
      </div>
      <div class="media">
        <slot name="media" />
      </div>
    </section>
    <section v-if="alignedRight" class="section">
      <div class="media">
        <slot name="media" />
      </div>
      <div class="content">
        <slot name="content" />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: "SectionContainer",
  props: {
    alignedRight: {
      type: Boolean,
      default: false,
    },
    contentWidth: {
      type: Number,
      default: 50,
    },
    alignCenter: {
      type: String,
      default: "center",
    },
  },
  data() {
    return {
      mediaW: `${100 - this.contentWidth}%`,
      contentW: `${this.contentWidth}%`,
    };
  },
};
</script>

<style scoped>
.section {
  display: flex;
  gap: 2rem;
  position: relative;
  margin: 2rem 0 3rem;
}

.section > div {
  min-width: 0;
}

.content {
  display: flex;
  width: v-bind(contentW);
  align-items: v-bind(alignCenter);
  justify-content: space-between;
}

.media {
  width: v-bind(mediaW);
  display: flex;
  align-items: center;
}

@media screen and (max-width: 1024px) {
  .section {
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 1.5rem;
  }
  .content,
  .media {
    width: 100%;
  }
}
</style>
