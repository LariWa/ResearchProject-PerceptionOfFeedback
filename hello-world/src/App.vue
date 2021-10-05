<template>
 <!--  <Mainpage /> -->
 <reading-page />
</template>

<script>
import Mainpage from "./components/Mainpage.vue";
import ReadingPage from "./components/ReadingPage.vue";

export default {
  name: "App",
  components: {
    Mainpage, ReadingPage
  },
};
</script>
