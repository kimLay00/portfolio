<template>
  <v-layout row justify-center align-center wrap class="mt-4 pt-2">
    <EducationLicences></EducationLicences>
    <Experience></Experience>
    <v-layout row justify-center align-center wrap class="mt-4 pt-2">
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Frontend</span>

          <span class="light-blue--text text--darken-1">Language</span>
        </h2>
        <br>
        <div v-for="($skillItem, $index) in frontendSkills" :key="`frontend${$index}Skills`">
          <strong>{{$skillItem.skills}}</strong>
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16"></v-progress-linear>
        </div>
      </v-flex>
      <v-flex xs12 sm12 md4 lg5 xl5 class="mx-2 pt-4">
        <h2>
          <span>Version</span>

          <span class="light-blue--text text--darken-1">Control</span>
        </h2>
        <br>
        <div v-for="($skillItem, $index) in versionControlSkills" :key="`versionControl${$index}Skills`">
          <strong>{{$skillItem.skills}}</strong>
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16"></v-progress-linear>
        </div>
      </v-flex>
      <div class="mt-4 pt-2">
        <v-btn
          href="https://docs.google.com/document/d/1WSR42FEgUahJuR_RArW1wz7TfUBlgj13zekRidmQgs4/edit?usp=sharing"
          target="_blank"
          color="light-blue"
          dark
          large
        >
          Download Resume
          <v-icon right dark>fas fa-file-download</v-icon>
        </v-btn>
      </div>
    </v-layout>
  </v-layout>
</template>

<script>
import EducationLicences from "./Components/EducationLicences";
import Experience from "./Components/Experience";

export default {
  metaInfo: {
    title: "Resume",
    titleTemplate: "%s ← Eldin's Space",
    meta: [
      { name: "viewport", content: "width=device-width, initial-scale=1" },
      {
        name: "description",
        content:
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
      },
      { charset: "utf-8" },
      { property: "og:title", content: "Eldin' Space" },
      { property: "og:site_name", content: "Eldin' Space" },
      { property: "og:type", content: "website" },
      { property: "og:url", content: "https://eldin.space" },
      {
        property: "og:image",
        content: "https://i.imgur.com/Dcz2PGx.jpg"
      },
      {
        property: "og:description",
        content:
          "Vue NUXT HTML CSS JavaScript Design Adobe XD Photoshop Coding Skills Resume Work Web Developer Front-End"
      }
    ]
  },
  components:{
    EducationLicences,
    Experience
  },
  data() {
    return {
      value: 0,
      frontendSkills:[
        {skills: "Vue", barValue: 0},
        {skills: "Javascript", barValue: 0},
        {skills: "Typescript", barValue: 0},
        {skills: "HTML", barValue: 0},
        {skills: "CSS/ SCSS", barValue: 0},
        {skills: "JQuery", barValue: 0},
        {skills: "Angular", barValue: 0},
      ],
      versionControlSkills:[
        {skills: "GIT", barValue: 0},
        {skills: "SVN", barValue: 0},
      ],
      bufferValue: 100,
      interval: 0
    };
  },
  mounted() {
    this.startBuffer();
  },

  beforeDestroy() {
    clearInterval(this.interval);
  },

  methods: {
    startBuffer() {
      this.interval = setInterval(() => { 
        console.warn("hihi");
          this.frontendSkills = [
            {skills: "Javascript", barValue: 90},
            {skills: "Vue", barValue: 80},
            {skills: "HTML", barValue: 80},
            {skills: "CSS/ SCSS", barValue: 80},
            {skills: "JQuery", barValue: 80},
            {skills: "Typescript", barValue: 65},
            {skills: "Angular", barValue: 60},
          ];
          this.versionControlSkills = [
            {skills: "GIT", barValue: 90},
            {skills: "SVN", barValue: 60},
          ];
        }, 800);
    }
  }
};
</script>
<style >
</style>

