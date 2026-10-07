<template lang="">
  <div class="EducationItem">
    <div class="year">
      <div class="qualYear">{{ startYear }}-{{ endYear }}</div>

      <div v-if="subtext" class="subtext">
        {{ subtext }}
      </div>
    </div>
    <div class="qualificationContainer">
      <div class="qualification">{{ qualification }}</div>

      <div class="qualInfo">{{ qualInfo }}</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "EducationItem",
  props: {
    startYear: { type: String },
    endYear: { type: String },
    subtext: { type: String },
    qualification: { type: String },
    qualInfo: { type: String },
  },
};
</script>
<style scoped>
.EducationItem {
  border-radius: 15px;
  border: 3px solid #657f56;
  display: flex;
  justify-content: space-between;
  min-height: 100px;
  margin-bottom: 20px;
}

.year {
  /* Typography */
  color: #000;
  text-align: right;
  font-family: Montserrat;
  font-size: clamp(0.5em, 0.6em + 0.5vw, 1.2em);
  font-style: normal;
  font-weight: 400;
  line-height: normal;

  /* Positioning */
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  /* Padding */
  padding: 1em;
}

.qualificationContainer {
  display: flex;
  flex-direction: column;
  flex-grow: 1;

  color: #000;
  text-align: right;
  font-family: Montserrat;

  font-style: italic;
  font-weight: 400;
  line-height: normal;

  min-width: 0;
  width: 60%;
  padding: 1rem 0.5rem;
}

.qualification {
  font-size: clamp(1rem, 0.836363636364rem + 0.606060606061vw, 1.2rem);
  flex-wrap: wrap;
}

.qualInfo {
  display: flex;
  font-size: clamp(0.9rem, 0.818181818182rem + 0.30303030303vw, 1rem);
  flex-wrap: wrap;
  justify-content: end;
}

@media screen and (max-width: 480px) {
  .EducationItem {
    flex-direction: column;
  }

  .year {
    align-items: flex-start;
    padding: 0.75rem 1rem 0;
    text-align: left;
  }

  .qualificationContainer {
    width: 100%;
    padding: 0.75rem 1rem;
    text-align: left;
  }

  .qualInfo {
    justify-content: flex-start;
  }
}
</style>
