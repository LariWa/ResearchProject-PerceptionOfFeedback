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
    <Quizpage v-if="quiz" v-bind:questions="questions" @finishPage="nextPage" />

    <div class="container mt-5" v-else>
      <div class="d-flex justify-content-between">
        <h3>MODULE 3</h3>
        <h4>Definition and Conceptualization of health literacy</h4>
      </div>

      <div class="box py-4">
        <h3 class="mt-0 h3-learning">LEARNING OBJECTIVE</h3>
        <h4 class="my-0">Describe health literacy and related issues</h4>
      </div>
      <p>
        Although the module concerns the introduction of digital health
        literacy, we are going to start by understanding the core element of
        digital health literacy, health literacy. Thus, in the first section, we
        will be looking at the definition of health literacy, antecedents of
        health literacy, its relationship to health outcomes, and related
        skills.
      </p>
      <h2><b>What is health literacy?</b></h2>
      <p>
        The term health literacy is a new concept in health-related studies, and
        only within the last decade have researchers started to discussed
        problems associated with it, the role it plays in an individual’s
        ability to comprehend health-related information, and its relationship
        to health outcomes (Sørensen et al., 2012). Health is not only a new
        concept to health researchers, but some of the health practionners are
        unaware of the health concept, and its importance. However, it is
        important to understand health literacy, because if a person does not
        have adequate health literacy or health-care provider is unaware of the
        person's level of health literacy, it will be difficult to generate
        person-centered health-care (Osborne, 2014).
        <br /><br />
        In the existing literature, health literacy is associated with various
        definitions and interpretations, and they vary based on different health
        domains, including health promotion, health-care, and disease
        prevention. According to the World Health Organization (WHO, 2013), a
        broad and inclusive definition of health literacy is:
      </p>

      <div class="box">
        <p class="box-quote">
          <em
            >“Health literacy is linked to literacy and entails people’s
            knowledge, motivation and competences to access, understand,
            appraise and apply health information in order to make judgments and
            take decisions in everyday life concerning health care, disease
            prevention and health promotion to maintain or improve quality of
            life during the life course.” (Sørensen et al., 2012; as cited in
            WHO, 2013 pp.4)”.</em
          >
        </p>
      </div>

      <hr />

      <h2>Conceptualization of health literacy</h2>
      <p>
        For a practice-oriented understanding of the above definition, the
        European Health Literacy Consortium developed an integrated conceptual
        model of health literacy (Figure 1), which identifies 4 dimensions of
        health literacy related to the ability to accessing, understanding,
        appraising, and applying health-related information. This model
        integrates medical and public views on health literacy. It was developed
        based on a systematic review that counted 17 peer-reviewed definitions
        and 12 previous conceptual frameworks and models of health literacy. As
        you may see, the model also noted the determinants factors and outcomes
        of health literacy (more discussed in the next sub-sections).
      </p>
      <img src="../assets/figure1.png" />
      <div class="figure-text d-flex justify-content-center">
        <span
          ><b>Figure1</b>: Integrated model of health literacy. The core part of
          the model shows the four dimensions of health literacy related to
          competencies of accessing, understanding, appraising and applying
          health-related information within health care, disease prevention and
          health promotion settings. The outer parts present the determinants
          factors of health literacy and the pathways to health outcomes.
          Source: (Sørensen et al., 2012).</span
        >
      </div>

      <div class="d-flex figure-2-box align-items-center">
        <img class="figure-2-img" src="../assets/figure2.png" />
        <div class="box figure-2-text">
          <p>
            Further, the European Health Literacy Consortium combined the four
            dimensions referring to health information processing with the three
            levels of health domains (health-care, disease prevention, and
            health promotion), and this yields a matrix with 12 dimensions of
            health Literacy as it is described in Table 1.
          </p>
        </div>
      </div>

      <hr />

      <h2>Health literacy environment</h2>
      <p>
        WHO (2013) noted that the European Health Literacy Consortium model can
        serve as a basis for developing interventions for improving health
        literacy, and has provided a conceptual basis for developing and
        validating measurement tools, capturing the dimensions of health
        literacy within health care, disease prevention, and health promotion
        settings.
      </p>

      <div class="box">
        <p>
          Although the European Health Literacy Consortium model is important,
          it only conceptualizes health literacy from the perceptive of
          individual abilities and knowledge. However, the range of evidence
          presented supports a wider and relational concept of health literacy
          that considers both individual abilities and knowledge and health
          literacy environment (see, figure 2) (Parker, 2009). 'Health literacy
          environment' is a mix of the infrastructure, policies, processes,
          materials, people and relationships of the health system can be set up
          and work in a way that makes it easier or more difficult for consumers
          to navigate, understand and use information and services about health
          and health care (Australian Commission on Safety and Quality in Health
          Care, 2014). The way the health literacy environment works, and how
          complex it is influences how individual make decisions and take
          actions about health. Thus, the envision of health literacy
          improvement should consider both individual abilities and the
          environment demands to ensure that people are in the best position to
          make decisions and take action about their health.
        </p>
      </div>
      <img src="../assets/figure3.png" />

      <div class="figure-text d-flex justify-content-center">
        <span
          ><b>Figure 2</b>. Health literacy. Health literacy is about both the
          individual’s skills and abilities, and the complexities of the
          contexts within which individuals act. (Parker, 2009)</span
        >
      </div>

      <h3 class="mt-5"><em>REFERENCES</em></h3>
      <hr />
      <ul>
        <li>
          WHO. (2013). Health literacy. The solid facts.
          https://apps.who.int/iris/handle/10665/326432
        </li>
        <li>
          Ruth Parker. (2009). Measuring Health Literacy: What? So What? Now
          What? https://www.ncbi.nlm.nih.gov/books/NBK45386/
        </li>
        <li>
          Sørensen, K., Van Den Broucke, S., Fullam, J., Doyle, G., Pelikan, J.,
          Slonska, Z., & Brand, H. (2012). Health literacy and public health: A
          systematic review and integration of definitions and models. BMC
          Public Health, 12(1), 80. https://doi.org/10.1186/1471-2458-12-80.
        </li>
        <li>
          Australian Commission on Safety and Quality in Health Care. (2014).
          Health Literacy: Taking action to improve safety and quality (Issue
          August).
          http://www.safetyandquality.gov.au/wp-content/uploads/2014/08/Health-Literacy-Taking-action-to-improve-safety-and-quality.pdf
        </li>
      </ul>

      <button class="quiz-button" @click="activateQuiz">Go to quiz</button>
    </div>
  </div>
</template>

<script>
import Progressbar from "./progress.vue";
import Quizpage from "./Quizpage.vue";

export default {
  name: "ReadingPage1",
  components: {
    Progressbar,
    Quizpage,
  },
  props: {},

  data: function() {
    return {
      quiz: false,
      questions: [
        {
          text: "What is true about health literacy?",
          responses: [
            {
              text:
                "It is about the ability to adopt good eating, hygiene, exercise, and sleeping behaviour.",
            },
            {
              text:
                "It is about the ability to handle basic medical care (e.g. measure body temperature, blood glucose level) on his/ her own.",
            },
            {
              text:
                "Health literacy is about the ability to obtain, process, understand, and use health information and services needed to maintain good health",
              correct: true,
            },
          ],
          feedback: "visualaudio", //visual, audio, visualaudio or none
        },

        {
          text:
            "Which of the following lists all of four dimensions of health literacy?",
          responses: [
            {
              text:
                "Access information, Understand information, appraise information, and apply information ",
              correct: true,
            },
            {
              text:
                "Assess health factors, interpret health information, make health decision and update oneself in a health environment",
            },
            {
              text:
                "Maintain health behavior, improve the ability to act in the health systems, prevent health problems, and improve health knowledge",
            },
            {
              text:
                "Health care, Disease prevention, Health promotion, and Health behavior.",
            },
          ],
          feedback: "visualaudio", //visual, audio, visualaudio or none
        },

        {
          text: "What is true about the health literacy environment?",
          responses: [
            {
              text:
                "It is about policies, processes, materials, people and relationships of the health system.",
            },
            {
              text:
                "It is about the demands and complexities placed on people who seek care in health systems.",
              correct: true,
            },
            {
              text:
                "It involves the broader range of materials such as applications form, rights postings, medical history forms, directives, and information booklets.",
            },
          ],
          feedback: "visualaudio", //visual, audio, visualaudio or none
        },
        {
          text:
            "Which one of the sub dimensions is under the health promotion domain?",
          responses: [
            {
              text:
                "The ability to regularly update oneself on determinants of health in the social and physical environment.",
              correct: true,
            },
            {
              text:
                "The ability to make informed decisions on medical issues and comply with medical advice.",
            },
            {
              text:
                "The ability to interpret and evaluate information on risk factors, and to make informed decisions on risk factors for health.",
            },
          ],
          feedback: "visualaudio", //visual, audio, visualaudio or none
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

  .box-quote {
    font-size: 15px;
    color: $color_darkPurple;
    font-weight: 600;
  }

  &.figure-2-text {
    border-radius: 50px 0 0 50px;
  }

  .h3-learning {
    color: rgba(13, 8, 68, 0.55);
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
