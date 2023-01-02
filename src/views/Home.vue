<template>
  <v-layout column justify-center align-center class="mt-4 pt-2">
    <VueCompareImage
      class="hidden-md-and-down"
      hover
      :style="{ minWidth: '1300px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage"
      :rightImage="rightImage"
      :sliderPositionPercentage="sliderPosition"
    />
    <VueCompareImage
      class="hidden-lg-and-up"
      hover
      :style="{ maxWidth: '400px' }"
      :sliderLineWidth="sliderLine"
      :handleSize="hSize"
      :leftImage="leftImage2"
      :rightImage="rightImage2"
      :sliderPositionPercentage="sliderPosition"
    />

    <br>

    <vue-typer class="headline" :repeat="0" text="Kimberly Lai"></vue-typer>
    <vue-typer
      :text="text1"
      :repeat="Infinity"
      :shuffle="false"
      initial-action="erasing"
      :pre-type-delay="70"
      :type-delay="70"
      :pre-erase-delay="1980"
      :erase-delay="150"
      erase-style="select-back"
      :erase-on-complete="false"
      caret-animation="smooth"
    ></vue-typer>
    <br>
    <v-flex xs12 sm6 md4 lg4 xl4>
      <v-card flat color="transparent" max-width="500">
        <v-card-title primary-title>
          <div>
            <h3 class="headline mb-0">
              <span>About</span>
              <span class="light-blue--text text--darken-1">Me</span>
            </h3>
            <div>
              <p>
                Hello! I'm Kimberly Lai. I'm a front-end developer who
                is passionate about code development and project management.
                I love doing yoga🧘🏻‍♀️ and travelling🌁 when I'm not coding. 
              </p>
            </div>
          </div>
        </v-card-title>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>
import { VueTyper } from "vue-typer";
import VueCompareImage from "vue-compare-image";

export default {
  components: {
    "vue-typer": VueTyper,
    VueCompareImage
  },
  data() {
    return {
      text1: ["Front-End Developer", "Web Developer", "Project Manager"],
      leftImage: require('../assets/homePage/selfIntroBanner_left.jpg'),
      rightImage: require('../assets/homePage/selfIntroBanner_right.jpg'),
      leftImage2: require('../assets/homePage/smallSelfIntroBanner_left.jpg'),
      rightImage2: require('../assets/homePage/smallSelfIntroBanner_right.jpg'),
      sliderLine: 0,
      hSize: 0,
      sliderPosition: 0.5,
    };
  }
};
</script>
<style>
@keyframes rocking {
  0%,
  100% {
    transform: rotateZ(-10deg);
  }

  50% {
    transform: rotateZ(10deg);
  }
}

.vue-typer {
  font-family: Arial, "Helvetica Neue", Helvetica, sans-serif;
}
.vue-typer .custom.char.typed {
  color: #039BE5;
}
.vue-typer .custom.char.selected {
  color: #0277BD;
}

.vue-typer .custom.caret {
  animation: rocking 1s ease-in-out 0s infinite;
}
.vue-typer .custom.caret.typing {
  background-color: #039BE5;
}
.vue-typer .custom.caret.selecting {
  display: inline-block;
  background-color: #0277BD;
}
</style>

