<template>

<div id="app">

<musicframe v-bind:currentSong="currentSong" v-bind:currentImage="currentImage"></musicframe>

<playlist v-bind:currentSong="currentSong" v-bind:currentImage="currentImage" @updateData="swapData($event)"></playlist>

</div>

</template>

<script>

import musicframe from './components/musicFrame'

import playlist from './components/playList'

export default {

  name: 'app',

  components: {

  'musicframe' : musicframe,
  'playlist' : playlist

},

  data () {
    return {
      currentSong : '',
      currentImage : 'src/assets/blah.jpg'
    }
  },

  methods: {
    swapData: function(data) {
     this.currentSong = data[0];
     this.currentImage = data[1];
    }
  }
}

</script>

<style scoped>

#app {
  clear : both;
}

</style>
