<template>
  <div class="hello">
    <h1>{{ "Title" }}</h1>
    <question v-bind:question="question1" />
  </div>
</template>

<script>
import question from "./question.vue";

export default {
  name: "Mainpage",
  components: {
    question,
  },
  data: function() {
    return {
      question1: {
        text: "Question 1",
        responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
        feedback: "visualaudio", //visual, audio, visualaudio or none
      },
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
