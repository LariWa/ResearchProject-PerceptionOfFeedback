<template>
  <div class="container">
    <div v-for="contentItem in pageContent" :key="contentItem">
      <Content v-bind:contentData="contentItem" v-bind:pageIndex="pageIndex" />
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
    pageIndex: Number,
  },

  data: function() {
    return {};
  },

  methods: {},
};
</script>
