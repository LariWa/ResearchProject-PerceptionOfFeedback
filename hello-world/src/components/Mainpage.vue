<template>
  <div class="hello">
    <h1>{{ "Title" }}</h1>
    <div v-for="(contentItem, index) in content" :key="contentItem">
      <div v-show="index == currentPage">
        Page {{ index }}
        <Page v-bind:pageContent="contentItem" />
      </div>
    </div>
    <button v-on:click="previous" v-show="isPrevious()">Previous</button>

    <button v-on:click="next" v-show="isNext()">
      Next
    </button>
  </div>
</template>

<script>
import Page from "./page.vue";

export default {
  name: "Mainpage",
  components: {
    Page,
  },
  methods: {
    next() {
      this.currentPage++;
    },
    previous() {
      this.currentPage--;
    },
    isNext() {
      return this.currentPage < this.content.length - 1;
    },
    isPrevious() {
      return this.currentPage > 0;
    },
  },

  data: function() {
    return {
      currentPage: 0,
      content: [
        [
          {
            text: "first text",
            question: {
              text: "Question 1",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "visualaudio", //visual, audio, visualaudio or none
            },
          },
          {
            text: "second text",
            question: {
              text: "Question 2",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "audio", //visual, audio, visualaudio or none
            },
          },
        ],

        //second page
        [
          {
            text: "second page first text",
            question: {
              text: "Question 1",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "visualaudio", //visual, audio, visualaudio or none
            },
          },
          {
            text: "second text",
            question: {
              text: "Question 2",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "audio", //visual, audio, visualaudio or none
            },
          },
        ],

        //third page
        [
          {
            text: "third page first text",
            question: {
              text: "Question 1",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "visualaudio", //visual, audio, visualaudio or none
            },
          },
          {
            text: "second text",
            question: {
              text: "Question 2",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "audio", //visual, audio, visualaudio or none
            },
          },
        ],
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
