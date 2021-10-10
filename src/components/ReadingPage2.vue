<template>
  <div>
    <div style="position: sticky; top: 0; z-index: 1;">
      <div class="bar">
        <div class="navbar-elements d-flex justify-content-around">
          <span>onelearnsQASystem</span>

          <div>
            <span class="mx-2">My Courses</span>
            <span class="mx-2">Syllabus</span>
            <span class="mx-2">Outline</span>
            <span class="mx-2"
              ><img
                class="user-icon"
                src="../assets/user_icon.png"
              />Username</span
            >
          </div>
        </div>
      </div>
      <div class="unit-elements text-center">
        <span class="mx-3">Unit 2: Digital Health Literacy</span>
        <span class="mx-3">></span>
        <span class="mx-3">Introduction to digital health literacy</span>
        <span class="mx-3 disabled-text"
          >Health Literacy in a digital ecosystem</span
        >
      </div>
      <Progressbar v-if="!quiz"></Progressbar>
    </div>
    <Quizpage
      v-if="quiz"
      v-bind:questions="questions"
      @finishPage="nextPage"
      v-bind:feedback="feedback"
    />
    <div class="container mt-5" v-else>
      <div class="d-flex justify-content-between">
        <h3>MODULE 3</h3>
        <h4>
          Determinant factors of health literacy &amp; <br />
          How is health literacy linked to health outcomes?
        </h4>
      </div>

      <div class="box py-4">
        <h3 class="mt-0 h3-learning">LEARNING OBJECTIVE</h3>
        <h4 class="my-0">Describe health literacy and related issues</h4>
      </div>
      <p>
        In the health literacy literature, a range of factors and personal
        characteristics have been identified as determinant factors affecting
        the skills and abilities of people to make decisions and take action
        about health and health care. Understanding these factors is important,
        as they may suggest places where action can be taken for health literacy
        improvement. The literature identified three main categories of such
        factors (Sørensen et al., 2012):
      </p>
      <div class="box box-purple">
        <h2><b>1) Environmental and societal factors:</b></h2>
      </div>
      <p>
        The environmental and societal factors which may influence health
        literacy include: Culture, Language, Political forces, and Societal
        systems (Sørensen et al., 2012).
      </p>

      <div class="box box-purple">
        <h2><b>2) Individual factors:</b></h2>
      </div>

      <p>
        The individual factors that may be considered as antecedents of health
        literacy include:
      </p>

      <p>
        <b>Individual characteristics</b> such as aging, gender, race,
        socioeconomic status, education, occupation, employment, and income.
        Concerning aging, a decline in an older adult's (65 and above) cognitive
        ability could contribute to the ability to comprehend and/or recall
        health information. Further, physical impairments such as hearing and
        vision loss may also contribute to a decreased ability to process health
        information (Sørensen et al., 2012).
      </p>

      <p>
        <b>Individual abilities</b> such as vision, hearing, speaking,
        reasoning, memory, and physical abilities; Individual skills associated
        with reading, comprehension, and numeracy; may lead to a progressively
        lower understanding of how to stay healthy and adhere to medication,
        when to seek medical attention, and properly follow medical regimens to
        recover from acute and care for chronic health conditions (Sørensen et
        al., 2012).
      </p>

      <p>
        <b>Personal health-related prior experience</b> (e.g., prior illness,
        awareness of healthcare delivery systems, exposure to medication) has
        also been identified as antecedents of health literacy that may
        contribute to developing an individual's health knowledge and potential.
        More simply put, individuals who had a health-related experience were
        exposed to the language of health care and cognitive framework that
        makes the health care information that was received seem logical
        (Speros, 2005). For example, individuals with chronic illness are likely
        to have more interaction with the health system and greater
        responsibility for participating in their care and treatment
        (Manganello, 2008).
      </p>

      <div class="box box-purple">
        <h2><b>3) Situational factors:</b></h2>
      </div>

      <p>
        <b>Physical environment, family, and peer influences:</b> <br /><br />
        Situational factors such as family and peers have been shown to have a
        direct influence on health literacy and health behavior. Considering the
        case of the youth, these factors can play a prominent role in the lives
        of youth as they transition into adolescence (Manganello, 2008).
      </p>

      <p>
        <b>Health and education institutions: </b> <br /><br />
        Other situational factors include health and education systems serve as
        potential contributors to the development of health literacy skills, and
        thus, act as possible areas for interventions. For instance, the
        education systems have a role in developing people's literacy as an
        integral part of health literacy. Therefore, how the education system is
        constituted may impact health literacy (Manganello, 2008).
      </p>

      <p>
        <b>Media use:</b> <br /><br />
        Media use may influence people's ability to access health information
        from mass media, understand the content, and evaluate the credibility of
        the information they obtain (Manganello, 2008).
      </p>

      <hr />

      <h3 class="mt-5 color-purple">Health literacy outcomes</h3>

      <p>
        A number of health literacy models have shown that an advanced level of
        health is beneficial to individual well-being, to the safety of health
        systems, and to the sustainable development of the whole community
        (Paasche-Orlow & Wolf, 2007; Sørensen et al., 2012; Ratzan, 2001).
      </p>

      <p class="color-purple mb-3">
        <b><em>Health literacy and individual benefits</em></b>
      </p>

      <p class="mt-0 mb-2">
        In terms of individual benefits, advanced health literacy leads to:
      </p>

      <ul class="px-3">
        <li>Improved knowledge of risks and health services.</li>
        <li>
          Better management of own health-care and health-care of family,
          including maintaining treatment and medication regimens.
        </li>
        <li>Improved interaction between healthcare providers.</li>
        <li>Improved capacity to act independently in the health systems.</li>
        <li>Improved motivation and more self-confidence.</li>
        <li>
          Improved individual resilience to social and economic adversity.
        </li>
      </ul>

      <p class="color-purple mb-3">
        <b><em>Health literacy and the safety of health-care systems</em></b>
      </p>

      <p class="mt-0 mb-2">
        In terms of health-care systems, advanced health literacy in the
        population is associated with:
      </p>

      <ul class="px-3">
        <li>Lower healthcare costs.</li>
        <li>Increased health knowledge.</li>
        <li>Shorter hospitalization.</li>
        <li>Less frequent use of healthcare services.</li>
      </ul>

      <p class="color-purple mb-3">
        <b><em>Health literacy and social and community benefits</em></b>
      </p>

      <p class="mt-0 mb-2">
        In terms of community and social benefits, advanced health literacy
        increases:
      </p>

      <ul class="px-3">
        <li>The citizens' participation in health programs.</li>
        <li>The citizens capacity to influence social norms.</li>
        <li>Good interaction with social groups.</li>
        <li>The citizens capacity to act on social and economic policies.</li>
        <li>The incentives to invest in children education.</li>
        <li>
          The incentives to invest in the labor market productivity and other
          important things including a pension scheme.
        </li>
      </ul>

      <h3 class="mt-5"><em>REFERENCES</em></h3>
      <hr />
      <ul>
        <li>
          Sørensen, K., Van Den Broucke, S., Fullam, J., Doyle, G., Pelikan, J.,
          Slonska, Z., &amp; Brand, H. (2012). Health literacy and public
          health: A systematic review and integration of definitions and models.
          BMC Public Health, 12(1), 80. https://doi.org/10.1186/1471-2458-12-80.
        </li>
        <li>
          Speros, C. (2005). Health literacy: Concept analysis. Journal of
          Advanced Nursing, 50(6), 633–640.
          https://doi.org/10.1111/j.1365-2648.2005.03448.x
        </li>
        <li>
          Paasche-Orlow, M. K., &amp; Wolf, M. S. (2007). The causal pathways
          linking health literacy to health outcomes. American Journal of Health
          Behavior, 31(SUPPL. 1). https://doi.org/10.5993/ajhb.31.s1.4
        </li>
        <li>
          Ratzan, S. (2001). Health literacy: communication for the public good.
          Health Promotion International, 16(2). https://doi.org/doi:
          10.1093/heapro/16.2.207
        </li>
        <li>
          Sørensen, K., Van Den Broucke, S., Fullam, J., Doyle, G., Pelikan, J.,
          Slonska, Z., &amp; Brand, H. (2012). Health literacy and public
          health: A systematic review and integration of definitions and models.
          BMC Public Health, 12(1), 80. https://doi.org/10.1186/1471-2458-12-80
        </li>
      </ul>

      <button class="quiz-button" @click="activateQuiz">Go to quiz</button>
    </div>
  </div>
</template>

<script>
import Quizpage from "./Quizpage.vue";
import Progressbar from "./progress.vue";

export default {
  name: "ReadingPage2",
  components: {
    Quizpage,
    Progressbar,
  },
  props: { feedback: String },

  data: function() {
    return {
      quiz: false,
      questions: [
        {
          text:
            "Bunyana is 72 years old woman, who is leaving in the countryside area of Bunagana. She did not attend schools, but she is a rich farmer. Among the following statement, what is true about Bunyana?",
          responses: [
            { text: "She may tend to use more of preventive care approaches" },
            {
              text: "She may tend to use less expensive health-care services.",
            },
            { text: "She may tend to use more medicine.", correct: true },
          ],
        },
        {
          text:
            "Kalisa is 19 years old, and he is a student at St Peter’s High school. Last year, Kalisa has recovered from tuberculosis from which he suffered for 3 years. Among, the following statements, what is true about Kalisa:",
          responses: [
            {
              text:
                "Kalisa would tend to use emergency services for infectious diseases.",
            },
            {
              text:
                "Kalisa would tend to use more expensive medicine against infectious diseases.",
            },
            {
              text:
                "Kalisa would tend to use more preventive methods to fight infectious diseases.",
              correct: true,
            },
          ],
        },
        {
          text: "Which of the following statements is correct?",
          responses: [
            {
              text:
                "It is common for everyone who is not a clinician or a pharmacist to misunderstand drug labels or have trouble following their directions.",
            },
            {
              text:
                "It is common for people living in rural and remote areas to misunderstand drug labels or have trouble following their directions.",
            },
            {
              text:
                "It is common for people with limited health literacy to misunderstand drug labels or have trouble following their directions.",
              correct: true,
            },
          ],
        },
        {
          text: "Which of the following statements is correct?",
          responses: [
            {
              text:
                "It is hard for everyone to know when it is appropriate to go to the emergency room rather than a primary care doctor.",
            },
            {
              text:
                "It is hard for people without medical training to know when it is appropriate to go to the emergency room rather than a primary care doctor.",
            },
            {
              text:
                "It is hard for people with limited health literacy to know when it is appropriate to go to the emergency room rather than a primary care doctor.",
              correct: true,
            },
          ],
        },
      ],
    };
  },

  methods: {
    activateQuiz: function() {
      this.quiz = true;
    },
    nextPage: function() {
      console.log("nextPage");
      this.$emit("nextPage");
    },
  },
};
</script>
<style lang="scss" scoped>
@import "../scss/app.scss";

.bar {
  background-color: $color_darkPurple;
  color: white;
  height: 70px;

  .navbar-elements {
    position: relative;
    top: 26px;

    .user-icon {
      width: 20px;
      margin-right: 5px;
    }
  }
}

.unit-elements {
  background-color: $color_lightPurple;
  height: 50px;
  padding-top: 16px;
  font-size: 18px;

  .disabled-text {
    color: rgba(13, 8, 68, 0.5);
  }
}

h2 {
  font-size: 36px;
  font-weight: 600;
  color: $color_darkBlue;
  margin-top: 50px;
}

h3 {
  font-size: 24px;
  color: $color_darkBlue;
  font-weight: 600;
}

h4 {
  font-size: 20px;
  color: black;
}

p {
  font-size: 18px;
  color: black;
  margin: 40px 0;
}

hr {
  border-top: 6px solid $color_darkPurple;
  margin: 30px 0;
  border-radius: 50px;
}

ul {
  padding: 0 100px;

  li {
    font-size: 13px;
  }
}

.box {
  background-color: $color_lightPink;
  padding: 3rem;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border-radius: 50px;
  margin: 30px 0;

  &.box-purple {
    background-color: $color_darkPurple;

    h2 {
      color: white;
      margin: 0;
      font-size: 24px;
    }
  }
}

.figure-text {
  color: $color_darkPurple;
  font-size: 14px;

  span {
    width: 800px;
  }
}

.figure-2-box {
  height: 500px;

  .figure-2-img {
    position: absolute;
    left: 40px;
    width: 800px;

    @media (min-width: 1600px) {
      width: 900px;
    }
  }

  .figure-2-text {
    position: absolute;
    right: 0px;
    width: 500px;
    padding-right: 150px;

    @media (min-width: 1600px) {
      width: 900px;
    }
  }
}

.quiz-button {
  width: 180px;
  height: 89px;
  box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.05);
  border: none;
  border-radius: 100px;
  font-size: 24px;
  margin: 100px 0px;
  background: $color_lightPink;
  color: $color_darkPurple;

  &:hover {
    background: $color_lilac;
    color: white;
  }

  &:active {
    outline: none !important;
  }
}

.quiz-button::after,
.quiz-button:hover::after {
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

.color-purple {
  color: $color_darkPurple;
}
/* play with some lines below */
#progress-container-el {
  /* background */
  background-color: transparent !important;
  top: calc(100% - 4px) !important; /* remove if Vue 3.x */
}
#progress-el {
  /* progress bar */
  background-color: red !important;
}
</style>
