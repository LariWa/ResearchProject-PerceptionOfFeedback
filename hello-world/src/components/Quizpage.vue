<template>
  <div class="hello">
    <!-- <h1>{{ "Title" }}</h1> -->
    <div v-for="(question, index) in questions" :key="index">
      <div v-show="index == currentPage">
        <!--  Page {{ index }} -->
        <div class="circle-menu mt-5">
          <div
            class="circle-1"
            :class="currentPage == 0 ? 'active-circle' : ''"
          >
            1
          </div>
          <div
            class="line"
            :class="currentPage < 1 ? 'inactive-line' : ''"
          ></div>
          <div
            class="circle-2"
            :class="
              currentPage == 1
                ? 'active-circle'
                : currentPage < 1
                ? 'inactive-circle'
                : ''
            "
          >
            2
          </div>
          <div
            class="line"
            :class="currentPage < 2 ? 'inactive-line' : ''"
          ></div>
          <div
            class="circle-3"
            :class="
              currentPage == 2
                ? 'active-circle'
                : currentPage < 2
                ? 'inactive-circle'
                : ''
            "
          >
            3
          </div>
          <div
            class="line"
            :class="currentPage < 3 ? 'inactive-line' : ''"
          ></div>
          <div
            class="circle-4"
            :class="
              currentPage == 3
                ? 'active-circle'
                : currentPage < 3
                ? 'inactive-circle'
                : ''
            "
          >
            4
          </div>
        </div>
        <Question v-bind:question="question" v-bind:pageIndex="currentPage" />
      </div>
    </div>

    <div class="container d-flex justify-content-between mb-5">
      <button
        class="previous-button"
        v-on:click="previous"
        v-show="isPrevious()"
      >
        Previous
      </button>

      <button class="next-button" v-on:click="next" v-show="isNext()">
        Next
      </button>
      <button
        class="next-button finish-button"
        v-on:click="finish"
        v-show="isFinalPage()"
      >
        Finish Section
      </button>
    </div>
    <div style="height: 100px"></div>
  </div>
</template>

<script>
import Question from "./question.vue";

export default {
  name: "Quizpage",
  props: {
    questions: Array,
  },
  components: {
    Question,
  },
  methods: {
    next() {
      this.currentPage++;
    },
    previous() {
      this.currentPage--;
    },
    isNext() {
      return this.currentPage < this.questions.length - 1;
    },
    isFinalPage() {
      return !(this.currentPage < this.questions.length - 1);
    },
    isPrevious() {
      return this.currentPage > 0;
    },
    finish() {
      console.log("send");
      this.$emit("finishPage");
    },
  },

  data: function() {
    return {
      currentPage: 0,
    };
  },
};
</script>
<style lang="scss" scoped>
@import "../scss/app.scss";

.container {
  position: relative;
}

.previous-button,
.next-button {
  width: 180px;
  height: 60px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border: none;
  border-radius: 100px;
  font-size: 20px;
  margin: 70px 0px;
  background: $color_lightPink;
  color: $color_darkPurple;
  position: absolute;
  top: -20px;

  &:hover {
    background: $color_lilac;
    color: white;
  }

  &:active {
    outline: none !important;
  }
}

.previous-button {
  left: 0;
}

.next-button {
  right: 0;
}
.finish-button {
  width: 300px;
  font-size: 1.75em;
}
.previous-button::before,
.previous-button:hover::before {
  content: "";
  display: inline-block;
  background: url("../assets/darkArrow.png");
  background-size: contain;
  background-repeat: no-repeat;
  width: 20px;
  height: 20px;
  transform: rotate(180deg);
  margin-right: 1rem;
}

.next-button::after,
.next-button:hover::after {
  content: "";
  display: inline-block;
  background: url("../assets/darkArrow.png");
  background-size: contain;
  background-repeat: no-repeat;
  width: 20px;
  height: 20px;
  margin-left: 1rem;
  position: relative;
  top: 6px;
}

.previous-button:hover::before,
.next-button:hover::after {
  background: url("../assets/whiteArrow.png") !important;
  background-size: contain !important;
  background-repeat: no-repeat !important;
}

.previous-button,
.next-button {
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
  .circle-1,
  .circle-2,
  .circle-3,
  .circle-4 {
    width: 45px;
    height: 45px;
    background: white;
    border: 5px solid $color_darkPurple;
    border-radius: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 32px;
    color: $color_darkPurple;
    font-weight: 600;
    box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  }

  .line {
    width: 140px;
    border-bottom: 8px solid $color_darkPurple;
    position: relative;
    bottom: 18px;

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
