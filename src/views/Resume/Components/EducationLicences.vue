<template>
    <v-flex xs12 sm12 md5 lg6 xl6 class="educationLiencesContainer mt-4 pt-4">
      <h2 class="mb-4 pl-4 pt-2">Education/ Licences</h2>
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
                <div class="caption mb-2">{{$timeLineItem.institute}}</div>
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
            {startDate: "JAN 2022", endDate: "PRESENT", title: "Project Management Profession (PMP)", institute: "Project Management Institute"},
            {startDate: "SEP 2013", endDate: "MAY 2017", title: "Bachelor of Engineering in Information Engineering", institute: "The Chinese University of Hong Kong"},
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