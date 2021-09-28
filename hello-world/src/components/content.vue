<template>
  <div>{{ contentData.text }}</div>
  <question v-bind:question="contentData.question" />
</template>

<script>
import question from "./question.vue";

export default {
  name: "Content",
  components: {
    question,
  },
  props: {
    contentData: Object,
  },
  data: function() {
    return {};
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
