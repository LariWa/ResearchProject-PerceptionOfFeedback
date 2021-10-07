<template>
  <div>
    <div class="question-style mx-auto align-items-center">
      <img
        class="question-triangle"
        src="../assets/triangle.png"
        :class="
          pageIndex == 0
            ? 'position-0'
            : pageIndex == 1
            ? 'position-1'
            : pageIndex == 2
            ? 'position-2'
            : pageIndex == 3
            ? 'position-3'
            : ''
        "
      />
      <h2>{{ question.text }}</h2>
    </div>
    <ul class="d-flex flex-column align-items-center" id="questionsList">
      <li
        class="answer-style d-flex align-items-center"
        v-for="(response, index) in question.responses"
        :key="response"
        :class="
          selected_answer === index && correctAnswer
            ? 'correct-answer'
            : selected_answer === index && !correctAnswer
            ? 'wrong-answer'
            : ''
        "
      >
        <label class="d-flex align-items-center">
          <img
            v-if="selected_answer === index && correctAnswer"
            class="confetti-left"
            src="../assets/confetti.gif"
          />
          <div class="d-flex">
            <input
              type="radio"
              v-bind:name="'1'"
              v-on:click="feedback(response.correct)"
              @change="onChange(index)"
            />
          </div>
          <div class="answer-text">
            {{ response.text }}
          </div>
          <img
            v-if="selected_answer === index && correctAnswer"
            class="confetti-right"
            src="../assets/confetti.gif"
          />
        </label>
      </li>
    </ul>
    <!-- visual feedback -->
    <div v-show="correctAnswer && question.feedback.includes('visual')"></div>
    <div
      v-show="
        selected && !correctAnswer && question.feedback.includes('visual')
      "
    ></div>
    <!-- audio feedback -->
  </div>
</template>

<script>
export default {
  name: "question",

  props: {
    question: Object,
    pageIndex: Number,
  },
  data: function() {
    return {
      correctAnswer: false,
      selected: false,
      correctAudio: new Audio(
        "http://freesoundeffect.net/sites/default/files/feedback-correct-3.wav-sound-effect-55313111.mp3"
      ),
      incorrectAudio: new Audio(
        "http://freesoundeffect.net/sites/default/files/feedback-incorrect-1.wav-sound-effect-41122437.mp3"
      ),
      selected_answer: -1,
    };
  },

  created: function() {},

  methods: {
    feedback(correct) {
      this.selected = true;

      if (correct) this.correctAnswer = true;
      else this.correctAnswer = false;
      //audio feedback
      if (this.question.feedback.includes("audio")) {
        this.resetAudio();
        if (correct) {
          this.correctAudio.play();
        } else {
          this.incorrectAudio.play();
        }
      }
    },
    resetAudio() {
      this.correctAudio.pause();
      this.correctAudio.currentTime = 0;
      this.incorrectAudio.pause();
      this.incorrectAudio.currentTime = 0;
    },
    onChange(index) {
      this.selected_answer = index;
      console.log(index);
    },
  },
};
</script>
<style lang="scss" scoped>
@import "../scss/app.scss";

.question-style {
  background-color: $color_lightPink;
  // height: 160px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 30px 30px;
  text-align: center;
  font-size: 24px;
  color: $color_darkBlue;
  filter: drop-shadow(0px 8px 15px rgb(0 0 0 / 0.05));
  border-radius: 50px;
  width: 900px;

  h2 {
    font-size: 24px;
  }

  .question-triangle {
    position: absolute;
    width: 100px;
    top: -60px;

    &.position-0 {
      left: 70px;
    }

    &.position-1 {
      left: 260px;
    }

    &.position-2 {
      left: 440px;
    }

    &.position-3 {
      left: 630px;
    }
  }
}

ul {
  list-style-type: none;
}
input {
  height: 70px;
  width: 70px;
  background-color: white;
  border-radius: 100px;
  border: 5px solid $color_lilac;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  margin: 0 0 0 80px;
}

.answer-style {
  padding: 0.5rem;
  margin-top: 25px;
  width: 750px;
  background-color: $color_lightPink;
  border-radius: 100px;
  color: $color_darkBlue;
  font-size: 16px;
  // height: 125px;

  .confetti-left {
    position: absolute;
    left: -200px;
    height: 220px;
  }

  .confetti-right {
    position: absolute;
    right: -200px;
    height: 220px;
  }
}

.answer-text {
  padding: 0 80px;
}

.correct-answer {
  background-color: white;
  border: 10px solid $color_green;
  color: $color_darkGreen;
  filter: drop-shadow(0px 8px 15px $color_green);

  input {
    border: 5px solid $color_green;

    &:checked {
      content: url("../assets/tick.png");
      padding: 8px;
    }
  }
}

.wrong-answer {
  background-color: white;
  border: 10px solid $color_red;
  color: #0d0844;
  filter: drop-shadow(0px 8px 15px $color_red);

  input {
    border: 3px solid $color_red;

    &:checked {
      content: url("../assets/x.png");
      padding: 8px;
    }
  }
}
</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
