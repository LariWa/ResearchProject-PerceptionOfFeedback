<template>
  <div class="progress-bar" id="myBar"></div>
</template>

<script>
export default {
  name: "progress",
  components: {},
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      var winScroll =
        document.body.scrollTop || document.documentElement.scrollTop;
      var height =
        document.documentElement.scrollHeight -
        document.documentElement.clientHeight;
      var scrolled = (winScroll / height) * 100;
      document.getElementById("myBar").style.width = scrolled + "%";
    },
  },
};
</script>
<style lang="scss" scoped>
@import '../scss/app.scss';

.header {
  position: fixed;
  top: 0;
  z-index: 1;
  width: 100%;
  background-color: #f1f1f1;
}

/* The progress container (grey background) */
.progress-container {
  width: 100%;
  height: 8px;
  background: #ccc;
}

/* The progress bar (scroll indicator) */
.progress-bar {
  height: 8px;
  background: $color_darkPurple !important;
  width: 0%;
}
</style>
