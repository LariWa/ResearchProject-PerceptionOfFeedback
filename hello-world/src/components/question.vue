<template>
  <div>
    <div class="question-style">
      <h2>{{ question.text }}</h2>
    </div>
    <ul class="d-flex flex-column align-items-center" id="questionsList">
      <li class="answer-style d-flex align-items-center" v-for="(response, index) in question.responses" :key="response" :class="((selected_answer === index) && correctAnswer) ? 'correct-answer' : ((selected_answer === index) && !correctAnswer) ? 'wrong-answer' : ''">
        <label class="d-flex align-items-center">
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
        </label>
      </li>
    </ul>
    <!-- visual feedback -->
    <div v-show="correctAnswer && question.feedback.includes('visual')">
      yeay correct answer
    </div>
    <div
      v-show="
        selected && !correctAnswer && question.feedback.includes('visual')
      "
    >
      oh no
    </div>
    <!-- audio feedback -->
  </div>
</template>

<script>
export default {
  name: "question",

  props: {
    question: Object,
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
  
  created: function () {

  },

  methods: {
    feedback(correct) {
      this.selected = true;

      if (correct) this.correctAnswer = true;
      else this.correctAnswer = false;
      //audio feedback
      if (this.question.feedback.includes("audio")) {
        if (correct) this.correctAudio.play();
        else this.incorrectAudio.play();
      }
    },
    onChange(index) {
      this.selected_answer = index;
        console.log(index);
    }
  },
};
</script>
<style scoped>
.question-style {
  background-color: #F3F6FF;
  height: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px;
  text-align: center;
  font-size: 36px;
  color: #0D0844;
  filter: drop-shadow(0px 8px 15px rgb(0 0 0 / 0.05));
  border-radius: 50px;
}

ul {
  list-style-type: none;
}
input {
/*   content: url('http://i.stack.imgur.com/M3EkO.png'); */
  height: 80px;
  width: 80px;
  background-color: white;
  border-radius: 100px;
  border: 5px solid #B0B3FF;
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  margin: 0 0 0 80px;
}
input:checked {
/*   content: url('http://i.stack.imgur.com/Ialva.png'); */
}
.answer-style {
  padding: 1rem;
  margin-top: 80px;
  width: 960px;
  background-color: #F3F6FF;
  border-radius: 100px;
  color: #0D0844;
  font-size: 24px;
  height: 165px;
}

.answer-text {
  padding: 0 80px;
}

.correct-answer {
  background-color: white;
  border: 10px solid #B6FFB0;
  color: #1F8816;
  filter: drop-shadow(0px 8px 15px #B6FFB0);
}

.correct-answer input {
  border: 5px solid #B6FFB0;
}

.wrong-answer {
  background-color: white;
  border: 10px solid red;
  color: red;
  filter: drop-shadow(0px 8px 15px red);
}

.wrong-answer input {
  border: 3px solid red;
}
</style>

<!-- Add "scoped" attribute to limit CSS to this component only -->
