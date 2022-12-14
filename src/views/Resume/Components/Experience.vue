<template>
    <v-flex xs12 sm12 md5 lg6 xl6 class="educationLiencesContainer mt-4 pt-4">
      <h2 class="mb-4 pl-4 pt-2">Experience</h2>
      <v-card-text class="py-0">
        <v-timeline align-top dense>

          <v-timeline-item v-for="($timeLineItem, $index) in timeLineItems" :key="`timeLineItem${$index}`" color="light-blue" small>
            <v-layout pt-3>
              <v-flex xs4>
                <div class="caption font-weight-bold light-blue--text text--darken-1">{{$timeLineItem.startDate}} -</div>
                <div class="caption font-weight-bold light-blue--text text--darken-1">{{$timeLineItem.endDate}}</div>
              </v-flex>
              <v-flex class="pl-2">
                <strong>{{$timeLineItem.title}}</strong>
                <div class="caption mb-2">{{$timeLineItem.company}}</div>
              </v-flex>
            </v-layout>
          </v-timeline-item>
        </v-timeline>
      </v-card-text>
    </v-flex>
</template>
<script>
    export default {
        name: "EducationLicences",
    data() {
        return {
        timeLineItems:[
            {startDate: "SEP 2021", endDate: "PRESENT", title: "Senior Web Developer", company: "Tranthink Technology Service Limited"},
            {startDate: "SEP 2019", endDate: "SEP 2021", title: "Frontend Programmer", company: "Tranthink Technology Service Limited"},
            {startDate: "JUL 2018", endDate: "AUG 2019", title: "Web Developer", company: "Metlife Hong Kong"},
            {startDate: "JUL 2017", endDate: "JUN 2018", title: "Consultant Trainee", company: "Orbit Consultancy Service Limited"},
        ],
        };
    },
    mounted() {
    },

    beforeDestroy() {
    },
    };
</script>
<style >
</style>