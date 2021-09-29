<template>
  <div class="hello">
    <h1>{{ "Title" }}</h1>
    <div v-for="(contentItem, index) in content" :key="contentItem">
      <div v-show="index == currentPage">
        Page {{ index }}
        <div class="circle-menu">
            <div class="circle-1" :class="currentPage == 0 ? 'active-circle' : ''">
              1
            </div>
            <div class="line" :class="currentPage < 1 ? 'inactive-line' : ''"></div>
            <div class="circle-2" :class="currentPage == 1 ? 'active-circle' : currentPage < 1 ? 'inactive-circle' : ''">
              2
            </div>
             <div class="line" :class="currentPage < 2 ? 'inactive-line' : ''"></div>
            <div class="circle-3" :class="currentPage == 2 ? 'active-circle' : currentPage < 2 ? 'inactive-circle' : ''">
              3
            </div>
             <div class="line" :class="currentPage < 3 ? 'inactive-line' : ''"></div>
            <div class="circle-4" :class="currentPage == 3 ? 'active-circle' : currentPage < 3 ? 'inactive-circle' : ''">
              4
            </div>
        </div>
        <Page v-bind:pageContent="contentItem" />
      </div>
    </div>

    <div class="container d-flex justify-content-between">
      <button class="previous-button" v-on:click="previous" v-show="isPrevious()">Previous</button>

      <button class="next-button" v-on:click="next" v-show="isNext()">
        Next
      </button>
    </div>
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
            text: "",
            question: {
              text: "Which of the following lists all of four dimensions of health literacy?",
              responses: [{ text: "Access information, Understand information, appraise information, and apply information ", correct: true }, { text: "Assess health factors, interpret health information, make health decision and update oneself in a health environment"}, { text: "Maintain health behavior, improve the ability to act in the health systems, prevent health problems, and improve health knowledge"}],
              feedback: "visualaudio", //visual, audio, visualaudio or none
            },
          },
          /* {
            text: "second text",
            question: {
              text: "Question 2",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "audio", //visual, audio, visualaudio or none
            },
          }, */
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
<style scoped>
.previous-button, .next-button {
  width: 289px;
  height: 89px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border: none;
  border-radius: 100px;
  font-size: 36px;
  margin: 100px 0px;
  background: #F3F6FF;
  color: #525497;
}

.next-button:hover, .previous-button:hover {
  background: #B0B3FF;
  color: white;
}

.next-button:active, .previous-button:active, .next-button:focus, .previous-button:focus {
  outline: none !important;
}

.circle-menu {
  display: flex;
  justify-content: center;
  align-content: center;
  margin-bottom: 80px;
}

.circle-menu .circle-1, .circle-menu .circle-2, .circle-menu .circle-3, .circle-menu .circle-4 {
  width: 64px;
  height: 64px;
  background: #FFFFFF;
  border: 5px solid #B0B3FF;
  border-radius: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 40px;
  color:#0D0844;
}

.circle-menu .line {
  width: 222px;
  border-bottom: 8px solid #B0B3FF;
  position: relative;
  bottom: 28px;
}

.circle-menu .line.inactive-line {
  border-bottom: 8px solid #C8D3F4;
}

.circle-menu .active-circle {
  background-color: #B0B3FF;
  color: white;
}

.circle-menu .inactive-circle {
  background-color: #F3F6FF;
  border: 5px solid #C8D3F4;
}
</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
