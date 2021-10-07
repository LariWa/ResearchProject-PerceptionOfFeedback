<template>
  <div>
    <div class="text">
      Please fill out this survey: <br />
      <a href="https://forms.gle/Rk1wjy7AEM5kyYB87" target="_blank"
        >https://forms.gle/Rk1wjy7AEM5kyYB87</a
      >
      <br />Then return to this page and continue.
    </div>
    <button class="next-button finish-button" v-on:click="next">Next</button>
  </div>
</template>
<script>
export default {
  name: "Surveypage",
  methods: {
    next() {
      this.$emit("nextPage");
    },
  },
};
</script>
<style lang="scss" scoped>
@import "../scss/app.scss";
.next-button {
  width: 180px;
  height: 60px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border: none;
  border-radius: 100px;
  font-size: 20px;
  background: $color_lightPink;
  color: $color_darkPurple;
  margin-top: 20px;
  margin-left: 60vw;
  &:hover {
    background: $color_lilac;
    color: white;
  }

  &:active {
    outline: none !important;
  }
}
.text {
  margin: auto;
  width: 50%;
  padding-top: 40vh;
  font-size: 26px;
  text-align: center;
}
</style>
