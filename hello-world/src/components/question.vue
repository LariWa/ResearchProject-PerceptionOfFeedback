<template>
  <div>
    <h2>{{ question.text }}</h2>
    <ol>
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
    </ol>
  </div>
</template>

<script>
export default {
  name: "question",

  props: {
    question: Object,
  },
  data() {},

  methods: {
    feedback(correct) {
      console.log("feedback" + correct);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
