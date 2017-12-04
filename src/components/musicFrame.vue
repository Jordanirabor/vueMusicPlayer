<template>

<div id="musicframe">

<div id="border">

<img v-bind:src="currentImage" width="100%" height="100%"/>

<div id="controls" @click="audioFunction">

<audio ref="audio" id="audio">

<source v-bind:src="currentSong">

Your browser does not support the audio element.

</audio>

<button>Play</button>
<button>Pause</button>
<button>Next</button>
<button>Previous</button>
</div>

</div>
</div>

</template>

<script>

import { bus } from '../main';

export default {
  name: 'music-frame',

props : {
 
 currentSong: {
  type : String
 },

 currentImage: {
  type : String
 }

  },
  data () {
    return {

    }
  },
  methods: {
    audioFunction: function(e){

      let value = e.target.innerText;

      switch(value) {

        case "Play" : {
              console.log(this.$refs.audio.play());
              break;
        }

        case "Pause" : {
              this.$refs.audio.pause();
              break;              
        }
      }

    }
  },
  created(){
    bus.$on('reload', () => {
    this.$refs.audio.load();
    this.$refs.audio.play();
    })
  }
}
</script>

<style>

#border {
    border: 10px solid black;
    border-radius: 15px;
    margin: 2rem 0.5rem;
    height: 30rem;
    width: 55%;
    float: left;
}

#controls {
  border: 10px solid white;
  border-radius: 15px;
  background: black;
  height: 5em;
}

#controls button{
  border:none;
  color: white;
  background: #172951;
  padding: 0.5em 3em;
  margin: 0.8em 1em;
  border-radius: 5px;
  font-size: 1em;
}
</style>
