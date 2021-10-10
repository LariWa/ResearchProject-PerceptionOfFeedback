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
          Components of digital health literacy <br />
          Barriers to achieving digital health literacy
        </h4>
      </div>

      <div class="box py-4">
        <h3 class="mt-0 h3-learning">LEARNING OBJECTIVE</h3>
        <h4 class="my-0">
          Recognize the transformation of health literacy to digital health
          literacy
        </h4>
      </div>
      <div class="box box-purple py-4">
        <h2><b>Digital health systems</b></h2>
      </div>
      <p>
        Advances in information technology present considerable promise to
        organizations as the Internet becomes a simple and effective means to
        deliver service and information. Delivery of services via the Internet
        is also called electronic services or digital services. There is a
        variety of such services including e-health for electronic health
        services, e-government for electronic government services, and so on.
        <br /><br />
        'E-health' also called 'Digital health' means digital health-related
        service delivery. It is generally seen as a tool for overcoming the
        challenges faced by traditional health-care sectors worldwide. The
        introduction of e-health came up with a lot of expectations, and it was
        considered as an approach to improve quality, capacity, efficiency, and
        access to health-care services and information, and thus holds the
        potential to promote health, and improve health equity. The huge
        potential that is attributed to e-health, is to balance an enormous and
        consistently growing health-care demand with limited resources, by using
        the Internet as a source for health information and service delivery
        (Jung, 2008).
      </p>

      <div class="box box-purple py-4">
        <h2><b>Digital health literacy</b></h2>
      </div>

      <p>
        Engaging in e-health systems, and handling health information on the
        Internet is a complex task for many people. It requires advanced skills
        that are far beyond the basic skills of health literacy. These skills
        are generally englobed in what is called “e-health literacy” or “digital
        health literacy”. <br /><br />
        In this section, we are going to discuss the definition and model of
        e-health literacy proposed by Norman & Skinner (2006) to describe the
        skills required to support full engagement within e-health systems.
        <br /><br />
        E-health literacy is: “the ability to seek, find, understand, and
        appraise health information from electronic sources and apply the
        knowledge gained to addressing or solving a health problem” (Norman &
        Skinner, 2006).
      </p>

      <div class="box box-purple py-4">
        <h2><b>Essential skills for digital health literacy</b></h2>
      </div>

      <div class="d-flex">
        <p class="flex-fill" style="width: 50%; padding: 30px 50px">
          The above e-health literacy definition is framed in terms of action
          because if one is looking for information about a health problem, one
          is looking not just for information but for actions that one can take
          in order to solve a health problem. Following that, Norman & Skinner
          (2006) identified six skills for people to be fully engaged able to
          take action in e-health systems:
        </p>

        <div class="box flex-fill" style="width: 20%">
          <em>
            <ol>
              <li>traditional literacy,</li>
              <li>health literacy,</li>
              <li>information literacy,</li>
              <li>scientific literacy,</li>
              <li>media literacy,</li>
              <li>computer literacy.</li>
            </ol>
          </em>
        </div>
      </div>

      <p>
        The relationship of these individual skills to each other is depicted in
        Figure 1, and Table 1 gives brief explanations.
      </p>

      <div class="d-flex">
        <div>
          <img style="width: 500px" src="../assets/figure4.jpg" />
          <span class="figure-text d-block"
            >Figure 1: Lily model. Through the metaphor of a lily, the petals
            (literacies) feed the pistil (e-health literacy), and yet the pistil
            overlaps the petals, tying them together. Source: Norman &amp;
            Skinner (2006).</span
          >
        </div>

        <div>
          <img
            style="width: 500px; height: 520px"
            src="../assets/figure5.jpg"
          />
          <span class="figure-text d-block"
            >Table1: Six skills of e-health (digital) literacy</span
          >
        </div>
      </div>

      <h4>E-health literacy domains</h4>

      <div class="box">
        <p>
          Based on the Lily model, a new framework of e-health literacy with
          consideration of the experiences of a wide range of stakeholders and
          in alignment with current technologies was developed (Norgaard et al.,
          2015). The new framework presented seven domains, classified into
          three groups, describing the range of strengths and weaknesses that
          people may have when attempting to engage in digital health. The seven
          domains of eHLF are:
        </p>
      </div>

      <p class="color-purple">
        <em><b>End-user capabilities:</b></em>
      </p>

      <ol>
        <li>Ability to process information.</li>
        <li>Engagement in one's own health.</li>
      </ol>

      <p class="color-purple">
        <em><b>End-users relationship with digital health systems:</b></em>
      </p>

      <ol>
        <li>Having access to systems that work.</li>
        <li>Digital services that suit individual needs.</li>
      </ol>

      <p class="color-purple">
        <em><b>End-user interaction experience with digital services:</b></em>
      </p>

      <ol>
        <li>Ability to engage actively with digital services.</li>
        <li>Feeling safe and in control.</li>
        <li>Motivation to engage with digital services.</li>
      </ol>

      <hr />

      <h3>Barriers to achieving digital health literacy</h3>

      <div class="d-flex">
        <p class="flex-fill" style="width: 50%; padding: 30px 50px">
          To generate the benefits of e-health service, nations and governments
          should enable users to strengthen the skills, knowledge, and resources
          they need to engage with the service at hand (Gilstad, 2014). A review
          of e-health literacy literature suggested five major barriers to the
          achievement of successful digital health literacy (Werts &
          Hutton-Rogers, 2013):
        </p>

        <div class="box d-flex flex-fill align-items-center" style="width: 50%">
          <ol>
            <li>Insufficient access to technological tools.</li>
            <li>Insufficient level of technology adoption.</li>
            <li>Insufficient level of technology proficiency.</li>
            <li>Low level of traditional health literacy.</li>
            <li>Low level of computer literacy.</li>
          </ol>
        </div>
      </div>

      <h3 class="mt-5"><em>REFERENCES</em></h3>
      <hr />
      <ul>
        <li>
          Jung, M. (2008). From Health to E-Health [Luleå University].
          http://epubl.ltu.se/1402-1544/2008/68/LTU-DT-0868-SE.pdf%5Cnhttps://pure.ltu.se/portal/files/2293451/LTU-DT-0868-SE.pdf
        </li>
        <li>
          Norgaard, O., Kayser, L., Osborne, R. H., &amp; Norgaard, O. (2015).
          The e-health literacy framework: A conceptual framework for
          characterizing e-health users and their interaction with e-health
          systems. Knowledge Management &amp; E-Learning, 7(4), 522–540.
        </li>
        <li>
          Norman, C. D., &amp; Skinner, H. A. (2006). eHealth literacy:
          Essential skills for consumer health in a networked world. Journal of
          Medical Internet Research, 8(2), 1–10.
          https://doi.org/10.2196/jmir.8.2.e9
        </li>
        <li>
          Gilstad, H. (2014). Toward a comprehensive model of eHealth literacy.
          CEUR Workshop Proceedings, 1251(Pahi), 63–72.
        </li>
        <li>
          Werts, N., &amp; Hutton-Rogers, L. (2013). Barriers To Achieving
          E-Health Literacy. American Journal of Health Sciences (AJHS), 4(3),
          115–120. https://doi.org/10.19030/ajhs.v4i3.8007
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
  name: "ReadingPage3",
  components: {
    Progressbar,
    Quizpage,
  },
  props: { feedback: String },

  data: function() {
    return {
      quiz: false,
      questions: [
        {
          text:
            "To seek, find, understand, and appraise health information from electronic sources require different skills, which are englobed in what is called digital health literacy. Among the following, which is irrelevant for digital health literacy?",
          responses: [
            { text: "The ability to use search engines." },
            { text: "The ability to read English", correct: true },
            { text: "The ability to understand relevant health terms." },
          ],
        },
        {
          text:
            "Which of the following is one of the major barriers to the achievement of digital health literacy in the population?",
          responses: [
            {
              text:
                "Poor interaction between health-care workers and health-consumers",
            },
            {
              text: "Lack of ability to navigate into the health systems.",
              correct: true,
            },
            { text: "Time to navigate into digital health systems." },
          ],
        },

        {
          text: "Which of the following statements is correct?",
          responses: [
            {
              text:
                "Limited digital literacy can increase health disparities in low-income countries.",
              correct: true,
            },
            {
              text:
                "A limited number of advanced e-health systems can increase health disparities in low-income countries.",
            },
            {
              text:
                "A limited number of health workers who understand the functionalities of e-health systems can increase health disparities in low-income countries.",
            },
          ],
        },

        {
          text:
            "The use of health information over the internet comes up with different advantages. Those include:",
          responses: [
            { text: "Insured anonymity while searching health information." },
            {
              text: "Quick access to the variety of health-behavior tips.",
              correct: true,
            },
            { text: "Access to organized and accurate information." },
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
  color: $color_darkBlue;
}

.figure-text {
  font-size: 14px;
  color: rgba(13, 8, 68, 0.55);
  padding: 15px;
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
