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
        <Page v-bind:pageContent="contentItem" v-bind:pageIndex="currentPage" />
      </div>
    </div>

    <div class="container d-flex justify-content-between">
      <button class="previous-button" v-on:click="previous" v-show="isPrevious()">
        Previous
      </button>

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
              text: "What is true about health literacy?",
              responses: [{ text: "It is about the ability to adopt good eating, hygiene, exercise, and sleeping behaviour." }, { text: "It is about the ability to handle basic medical care (e.g. measure body temperature, blood glucose level) on his/ her own."}, { text: "Health literacy is about the ability to obtain, process, understand, and use health information and services needed to maintain good health", correct: true }],
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

        //second page
        [
          {
            text: "",
            question: {
              text: "Which of the following lists all of four dimensions of health literacy?",
              responses: [{ text: "Access information, Understand information, appraise information, and apply information ", correct: true }, { text: "Assess health factors, interpret health information, make health decision and update oneself in a health environment"}, { text: "Maintain health behavior, improve the ability to act in the health systems, prevent health problems, and improve health knowledge"}, { text: "Health care, Disease prevention, Health promotion, and Health behavior."}],
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
              text: "What is true about the health literacy environment?",
              responses: [{ text: "It is about policies, processes, materials, people and relationships of the health system." }, { text: "It is about the demands and complexities placed on people who seek care in health systems.", correct: true }, { text: "It involves the broader range of materials such as applications form, rights postings, medical history forms, directives, and information booklets."}],
              feedback: "visualaudio", //visual, audio, visualaudio or none
            },
          },
      /*     {
            text: "second text",
            question: {
              text: "Question 2",
              responses: [{ text: "Wrong" }, { text: "Right!", correct: true }],
              feedback: "audio", //visual, audio, visualaudio or none
            },
          }, */
        ],
      ],
    };
  },
};
</script>
<style lang="scss" scoped>
@import '../scss/app.scss';

.previous-button, .next-button {
  width: 289px;
  height: 89px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border: none;
  border-radius: 100px;
  font-size: 36px;
  margin: 100px 0px;
  background: $color_lightPink;
  color: $color_darkPurple;

  &:hover {
    background: $color_lilac;
    color: white;
  }

  &:active {
    outline: none !important;
  }
}

.previous-button::before, 
.previous-button:hover::before {
  content: ''; 
  display: inline-block;
  background: url('../assets/darkArrow.png');
  background-size: contain;
  background-repeat: no-repeat;
  width: 30px;
  height: 30px;
  transform: rotate(180deg);
  margin-right: 1rem;
}

.next-button::after, 
.next-button:hover::after {
  content: ''; 
  display: inline-block;
  background: url('../assets/darkArrow.png');
  background-size: contain;
  background-repeat: no-repeat;
  width: 30px;
  height: 30px;
  margin-left: 1rem;
  position: relative;
  top: 8px;
}

.previous-button:hover::before, 
.next-button:hover::after {
  background: url('../assets/whiteArrow.png') !important;
  background-size: contain !important;
  background-repeat: no-repeat !important;
}

.previous-button,
.next-button  {
  .arrow { 
   width: 30px;
  }
}

.previous-button .arrow {
  transform: rotate(180deg);
}

.circle-menu {
  display: flex;
  justify-content: center;
  align-content: center;
  margin-bottom: 80px;
}

.circle-menu {
   .circle-1, .circle-2, .circle-3, .circle-4 { 
    width: 64px;
    height: 64px;
    background: white;
    border: 5px solid $color_darkPurple;
    border-radius: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 40px;
    color:$color_darkPurple;
    font-weight: 600;
    box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
   }

   .line {
    width: 222px;
    border-bottom: 8px solid $color_darkPurple;
    position: relative;
    bottom: 28px;

    &.inactive-line {
      border-bottom: 8px solid $color_lightPurple;
    }
   }

  .active-circle {
    background-color: $color_darkPurple;
    color: white;
  }

  .inactive-circle {
    background-color: white;
    border: 5px solid $color_lightPurple;
  }
}

</style>
<!-- Add "scoped" attribute to limit CSS to this component only -->
