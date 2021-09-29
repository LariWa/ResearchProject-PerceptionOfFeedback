<template>
  <div class="container">
    <div v-for="contentItem in pageContent" :key="contentItem">
      <Content v-bind:contentData="contentItem" />
    </div>
  </div>
</template>

<script>
import Content from "./content.vue";
export default {
  name: "page",
  components: {
    Content,
  },
  props: {
    pageContent: Array,
  },

  data: function() {
    return {};
  },

  methods: {},
};
</script>
