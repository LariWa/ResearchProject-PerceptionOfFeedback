<template>
<div>
    <Mainpage v-if="quiz" />
    <div class="container" v-else>
        <h3>MODULE 3 </h3>
        <h2>Definition and Conceptualization of health literacy</h2>

        <div class="box">
            <h2>LEARNING OBJECTIVE</h2>
            <p>Describe health literacy and related issues</p>
        </div>

        <p>Although the module concerns the introduction of digital health literacy, we are going to start by understanding the core element of digital health literacy, health literacy. Thus, in the first section, we will be looking at the definition of health literacy, antecedents of health literacy, its relationship to health outcomes, and related skills.</p>
        <h3><b>What is health literacy?</b></h3>
        <p>
            The term health literacy is a new concept in health-related studies, and only within the last decade have researchers started to discussed problems associated with it, the role it plays in an individual’s ability to comprehend health-related information, and its relationship to health outcomes (Sørensen et al., 2012). Health is not only a new concept to health researchers, but some of the health practionners are unaware of the health concept, and its importance. However, it is important to understand health literacy, because if a person does not have adequate health literacy or health-care provider is unaware of the person's level of health literacy, it will be difficult to generate person-centered health-care (Osborne, 2014).
            <br>
            In the existing literature, health literacy is associated with various definitions and interpretations, and they vary based on different health domains, including health promotion, health-care, and disease prevention. According to the World Health Organization (WHO, 2013), a broad and inclusive definition of health literacy is:
            <br>
            “Health literacy is linked to literacy and entails people’s knowledge, motivation and competences to access, understand, appraise and apply health information in order to make judgments and take decisions in everyday life concerning health care, disease prevention and health promotion to maintain or improve quality of life during the life course.” (Sørensen et al., 2012; as cited in WHO, 2013 pp.4)”.
        </p>

        <h3>Conceptualization of health literacy</h3>
        <p>For a practice-oriented understanding of the above definition, the European Health Literacy Consortium developed an integrated conceptual model of health literacy (Figure 1), which identifies 4 dimensions of health literacy related to the ability to accessing, understanding, appraising, and applying health-related information. This model integrates medical and public views on health literacy. It was developed based on a systematic review that counted 17 peer-reviewed definitions and 12 previous conceptual frameworks and models of health literacy. As you may see, the model also noted the determinants factors and outcomes of health literacy (more discussed in the next sub-sections).</p>
        <img />
        <span><b>Figure1</b>: Integrated model of health literacy. The core part of the model shows the four dimensions of health literacy related to competencies of accessing, understanding, appraising and applying health-related information within health care, disease prevention and health promotion settings. The outer parts present the determinants factors of health literacy and the pathways to health outcomes. Source: (Sørensen et al., 2012).</span>
        <p>Further, the European Health Literacy Consortium combined the four dimensions referring to health information processing with the three levels of health domains (health-care, disease prevention, and health promotion), and this yields a matrix with 12 dimensions of health Literacy as it is described in Table 1.</p>

        <h3>Health literacy environment</h3>
        <p>
            WHO (2013) noted that the European Health Literacy Consortium model can serve as a basis for developing interventions for improving health literacy, and has provided a conceptual basis for developing and validating measurement tools, capturing the dimensions of health literacy within health care, disease prevention, and health promotion settings.
            <br>
            Although the European Health Literacy Consortium model is important, it only conceptualizes health literacy from the perceptive of individual abilities and knowledge. However, the range of evidence presented supports a wider and relational concept of health literacy that considers both individual abilities and knowledge and health literacy environment (see, figure 2) (Parker, 2009). 'Health literacy environment' is a mix of the infrastructure, policies, processes, materials, people and relationships of the health system can be set up and work in a way that makes it easier or more difficult for consumers to navigate, understand and use information and services about health and health care (Australian Commission on Safety and Quality in Health Care, 2014). The way the health literacy environment works, and how complex it is influences how individual make decisions and take actions about health. Thus, the envision of health literacy improvement should consider both individual abilities and the environment demands to ensure that people are in the best position to make decisions and take action about their health.
        </p>

        <img />
        <span><b>Figure 2</b>. Health literacy. Health literacy is about both the individual’s skills and abilities, and the complexities of the contexts within which individuals act. (Parker, 2009)</span>
        
        <div class="box">
            <h3>REFERENCES</h3>
            <ul>
                <li>WHO. (2013). Health literacy. The solid facts. https://apps.who.int/iris/handle/10665/326432</li>
                <li>Ruth Parker. (2009). Measuring Health Literacy: What? So What? Now What? https://www.ncbi.nlm.nih.gov/books/NBK45386/</li>
                <li>Sørensen, K., Van Den Broucke, S., Fullam, J., Doyle, G., Pelikan, J., Slonska, Z., & Brand, H. (2012). Health literacy and public health: A systematic review and integration of definitions and models. BMC Public Health, 12(1), 80. https://doi.org/10.1186/1471-2458-12-80.</li>
                <li>Australian Commission on Safety and Quality in Health Care. (2014). Health Literacy: Taking action to improve safety and quality (Issue August). http://www.safetyandquality.gov.au/wp-content/uploads/2014/08/Health-Literacy-Taking-action-to-improve-safety-and-quality.pdf</li>
            </ul>
        </div>
        <button @click="activateQuiz">go to quiz</button>
    </div>
        
</div>
</template>

<script>
import Mainpage from "./Mainpage.vue";
export default {
  name: "ReadingPage",
  components: {
    Mainpage
  },
  props: {
   
  },

  data: function() {
    return {
        quiz: false,
    };
  },

  methods: {
      activateQuiz: function () {
        this.quiz = true;
      }
  },
};
</script>
