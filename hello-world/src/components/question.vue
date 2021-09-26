<template>
  <div>
    <h2>{{ question.text }}</h2>

    <li v-for="response in question.responses" :key="response">
      <label>
        <input
          type="radio"
          v-bind:name="'1'"
          v-on:click="feedback(response.correct)"
        />
        {{ response.text }}
      </label>
    </li>
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
    };
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
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
