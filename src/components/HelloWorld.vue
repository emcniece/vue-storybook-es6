<template>
  <v-container>
    <v-layout text-xs-center wrap>
      <v-flex xs12>
        <v-img
          :src="require('../assets/logo.svg')"
          class="my-3"
          contain
          height="200"
        ></v-img>
      </v-flex>

      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">
          Welcome to Vuetify
        </h1>
      </v-flex>

      <v-flex mb-5 xs12>
        <h2 class="headline font-weight-bold mb-3">Dynamic Carousel Data</h2>

        <v-btn v-on:click="addSlide">Add Slide</v-btn>

        <carousel :spacePadding="10">
          <slide v-for="(slide, i) in slides" :key="i" class="slide">
            {{ slide.text }}
          </slide>
        </carousel>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";

export default {
  components: { Carousel, Slide },
  data: () => ({
    slides: [
      {
        text: "Slide 1"
      },
      {
        text: "Slide 2"
      }
    ]
  }),
  methods: {
    addSlide: function(e) {
      this.slides.push({ text: `Slide ${this.slides.length + 1}` });
    }
  }
};
</script>

<style>
.slide {
  padding: 3em 0;

  background: rgba(0, 0, 0, 0.1);
}
</style>
