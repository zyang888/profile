<template>
  <div>
    <b-jumbotron>
      <template v-slot:header>CourseProject</template>
      <template v-slot:lead>
        Use the Mixin button below and the submit button on form page to see Mixin function
      </template>
      <hr class="my-4">
      <nuxt-link to="/Grid" class="text-warning">Grid</nuxt-link><p>Refactored into components with props & validation</p>
      <nuxt-link to="/Images" class="text-success">Images</nuxt-link><p>Images are all taken from an array and implemented using a v-for.</p>
      <nuxt-link to="/Form" class="text-danger">Form</nuxt-link><p>Creation and use of slot for header component</p>
      <client-only>
      <Game></Game>
      </client-only>
    </b-jumbotron>
    <b-button @click="clicked('Mixin 1 Triggered')" variant="primary" href="#">Mixin 1</b-button>
    <b-button @click="clicked('Mixin 2 Triggered')" variant="success" href="#">Mixin 2</b-button>
    <!-- <img v-bind:src="image"> -->
    <img v-show="!toggle" src="@/assets/OFFbulb.jpg">
    <img v-show="toggle" src="@/assets/ONbulb.jpg">
  </div>
</template>

<script>
import Game from '~/components/game'
import myButton from '@/mixins/myButton'

export default {
  name: 'home',
  components: {
    Game
  },
  data () {
    return {
      toggle: false
    }
  },
  mixins: [myButton],
  head () {
    return {
      title: 'HTML300 Project Page',
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        { hid: 'index', name: 'index', content: 'HTML300 Project Page' }
      ]
    }
  },
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Teko:700');

    canvas{
        border: 1px solid #000;
        display: block;
        margin: 0 auto;
    }
</style>
