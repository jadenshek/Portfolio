<template>
  <div class="sectionContainer">
    <div class="midText">
      <p>
        If you have any questions about tutoring, don’t hesitate to contact me
        at
      </p>
    </div>
    <EmailItem :email="email" />
  </div>
</template>

<script>
import EmailItem from "../Utility/Email/EmailItem.vue";
let links = require("@/assets/api/links.json");

export default {
  name: "MidCard",
  components: { EmailItem },
  data() {
    return {
      email: links.email,
    };
  },
};
</script>

<style scoped>
.sectionContainer {
  background-color: #476039;
  width: 100%;
  padding: 1rem;
}

p {
  font-family: montserrat-semiBold;

  font-style: normal;
  font-weight: 600;
  text-align: center;
  letter-spacing: 0.15em;

  color: #82a070;
}
h3 {
  font-family: montserrat-semiBold;
  font-style: normal;
  font-weight: 600;
  font-size: clamp(1rem, 0.836363636364rem + 0.606060606061vw, 1.2rem);
  line-height: 44px;

  /* identical to box height */
  text-align: center;
  letter-spacing: 0.15em;

  color: #d7ecc9;
}
</style>
