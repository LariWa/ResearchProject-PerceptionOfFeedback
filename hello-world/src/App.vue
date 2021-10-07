<template>
  <!--  <Mainpage /> -->
  <div>
    <ReadingPage1
      @nextPage="nextPage"
      v-show="currentPage == 0"
      v-bind:feedback="this.Feedbacktypes[indexes[0]]"
    />
    <ReadingPage2
      @nextPage="nextPage"
      v-show="currentPage == 2"
      v-bind:feedback="this.Feedbacktypes[indexes[1]]"
    />
    <ReadingPage3
      @nextPage="nextPage"
      v-show="currentPage == 4"
      v-bind:feedback="this.Feedbacktypes[indexes[2]]"
    />
    <FinalPage v-show="currentPage == 6" />
    <SurveyPage
      @nextPage="nextPage"
      v-show="currentPage == 1 || currentPage == 3 || currentPage == 5"
    />
  </div>
</template>

<script>
import ReadingPage1 from "./components/ReadingPage1.vue";
import ReadingPage2 from "./components/ReadingPage2.vue";
import ReadingPage3 from "./components/ReadingPage3.vue";
import FinalPage from "./components/FinalPage.vue";
import SurveyPage from "./components/SurveyPage.vue";

export default {
  name: "App",
  components: {
    ReadingPage1,
    ReadingPage2,
    ReadingPage3,
    FinalPage,
    SurveyPage,
  },
  data: function() {
    return {
      currentPage: 0,
      Feedbacktypes: ["visual", "audio", "visualaudio"],
      indexes: [0, 1, 2].sort(() => Math.random() - 0.5),
    };
  },
  methods: {
    nextPage() {
      this.currentPage++;
    },
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
