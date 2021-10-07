<template>
  <!--  <Mainpage /> -->
  <ReadingPage />
</template>

<script>
import ReadingPage from "./components/ReadingPage1.vue";

export default {
  name: "App",
  components: {
    ReadingPage,
  },
};
</script>
<style>
/* play with some lines below */
#progress-container-el {
  /* background */
  background-color: transparent !important;
  top: calc(100% - 4px) !important; /* remove if Vue 3.x */
}
#progress-el {
  /* progress bar */
  background-color: red !important;
}
</style>
