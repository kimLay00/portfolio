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
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16">
            <strong class="white--text">{{ $skillItem.barValue }}</strong>
          </v-progress-linear>
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
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16">
            <strong class="white--text">{{ $skillItem.barValue }}</strong>
          </v-progress-linear>
        </div>
        <h2>
          <span>Server</span>

          <span class="light-blue--text text--darken-1">Language</span>
        </h2>
        <br>
        <div v-for="($skillItem, $index) in serverLanguage" :key="`serverLang${$index}`">
          <strong>{{$skillItem.skills}}</strong>
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16">
            <strong class="white--text">{{ $skillItem.barValue }}</strong>
          </v-progress-linear>
        </div>
        <h2>
          <span>Database</span>
        </h2>
        <br>
        <div v-for="($skillItem, $index) in database" :key="`database${$index}`">
          <strong>{{$skillItem.skills}}</strong>
          <v-progress-linear v-model="$skillItem.barValue" :buffer-value="bufferValue" color="light-blue" height="16">
            <strong class="white--text">{{ $skillItem.barValue }}</strong>
          </v-progress-linear>
        </div>

      </v-flex>
      <div class="mt-4 pt-2">
        <v-btn
          target="_blank"
          href="https://docs.google.com/document/d/1aLNTN10IxfInONh1OFt6XVMM92O5PT-3OW-Uk1zPLKU/edit"
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
      serverLanguage:[
        {skills: "Node.js", barValue: 0},
      ],
      database:[
        {skills: "MSSQL", barValue: 0},
        {skills: "MongoDB", barValue: 0},
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
          this.frontendSkills = [
            {skills: "Javascript", barValue: 90},
            {skills: "HTML", barValue: 90},
            {skills: "CSS/ SCSS", barValue: 90},
            {skills: "JQuery", barValue: 90},
            {skills: "Vue", barValue: 80},
            {skills: "Typescript", barValue: 75},
            {skills: "Angular", barValue: 60},
          ];
          this.versionControlSkills = [
            {skills: "GIT", barValue: 90},
            {skills: "SVN", barValue: 60},
          ];
          this.serverLanguage = [
            {skills: "Node.js", barValue: 75},
          ];
          this.database = [
            {skills: "MSSQL", barValue: 80},
            {skills: "MongoDB", barValue: 70},
          ];
        }, 800);
    }
  }
};
</script>
<style >
</style>

