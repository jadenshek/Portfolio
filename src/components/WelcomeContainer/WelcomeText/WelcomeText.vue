<template lang="">
  <div id="WelcomeText">
    <div class="intro"><h1>Hi! I'm Jaden</h1></div>
    <div class="flavourText">
      <h2>I am a student and I like to make things!</h2>
    </div>
    <div class="greeting"><p>Welcome to my website!</p></div>
  </div>
</template>
<script>
export default {
  name: "WelcomeText",
};
</script>
<style scoped>
#WelcomeText {
  min-height: 20vh;
  text-align: left;
  position: relative;
  width: 100%;
}

h1,
h2,
h3 {
  font-family: Montserrat;
  font-style: normal;
  line-height: normal;
}

h1 {
  color: #476039;
  text-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.25);
  font-size: clamp(1.5rem, 0.272727272729rem + 4.54545454545vw, 3rem);
  font-weight: 700;
  text-transform: uppercase;
}

h2 {
  font-size: clamp(1rem, 0.181818181819rem + 3.0303030303vw, 2rem);
}
</style>
