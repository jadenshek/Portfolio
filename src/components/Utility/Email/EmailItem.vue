<template lang="">
  <div class="email">
    <h3>
      <a :href="mailto" title="Click me to send me an email!">{{ email }}</a>
    </h3>
  </div>
</template>
<script>
export default {
  name: "emailItem",
  props: {
    email: { type: String },
    subject: { type: String, default: "Tutoring" },
  },
  data() {
    return { mailto: `mailto:${this.email}?subject=${this.subject}` };
  },
};
</script>
<style scoped>
a {
  text-decoration: none;
  color: #d7ecc9;
}

h3 {
  font-family: montserrat-semiBold;
  font-style: normal;
  font-weight: 600;
  font-size: clamp(0.9rem, 0.818181818182rem + 0.30303030303vw, 1rem);
  line-height: 1.5;
  overflow-wrap: anywhere;

  /* identical to box height */
  text-align: center;
  letter-spacing: 0.15em;
}

a:hover {
  color: #fff;
}
</style>
