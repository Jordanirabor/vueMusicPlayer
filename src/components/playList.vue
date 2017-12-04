<template>

  <div id="playlist">

    <div id="secborder" ref="playlist" @click="changeSource">

    <div class="song" url-value="http://sami-server.info/hossein2/95/11/Music/06/Ed%20Sheeran%20-%20Shape%20Of%20You.mp3" picture-value="https://www.billboard.com/files/media/ed-sheeran-july-2017-billboard-1548.jpg"> Ed Sheeran  &nbsp;∘ &nbsp; Shape of you </div>
    <div class="song" url-value="http://jweb.taconic.net/music/linkin_park-faint.mp3" picture-value="https://orig00.deviantart.net/65e3/f/2009/335/6/2/linkin_park__faint_by_jimeye.jpg">Linkin Park &nbsp;∘&nbsp; Faint</div>
    <div class="song" url-value="http://dl.asra-music.com/foreign%20full%20album/Pink/Pink%20-%20The%20Truth%20About%20Love%20(2012)/04%20-%20Just%20Give%20Me%20A%20Reason.mp3" picture-value="https://i.ytimg.com/vi/3pDj1U6Zd08/maxresdefault.jpg">Pink &nbsp;∘&nbsp; Just give me a reason</div>
    <div class="song" url-value="http://tegos.kz/new/mp3_full/Clean_Bandit_-_Symphony.mp3" picture-value="https://i.ytimg.com/vi/jtTI-XuW8i8/maxresdefault.jpg"> Clean Bandit &nbsp;∘&nbsp; Symphony</div>    <div class="song" url-value="http://zaycev-mp3.net/mp3/linkin_park_powerless_[zaycev-mp3.net].mp3" picture-value="https://wallpapercave.com/wp/ufT9VZa.jpg">Linkin Park &nbsp;∘&nbsp; Powerless</div>
    <div class="song" url-value="http://rm.sina.com.cn/wm/VZ2008072314565310537VK/music/MUSIC0807231507294087.mp3" picture-value="https://i.ytimg.com/vi/oY5BYjsrIHk/maxresdefault.jpg">Linkin Park &nbsp;∘&nbsp; Somewhere I belong</div>
    <div class="song" url-value="http://s4.faz-dl.xyz/mr-reese/single/july2017/week1/Rihanna%20-%20Wild%20Thoughts%20Solo%20Version%20-%20MP3%20320.mp3" picture-value="http://thetropixs.com/wp-content/uploads/2017/06/Rihanna-Wild.jpg"> Rihanna &nbsp;∘&nbsp; Wild thoughts</div>
    <div class="song" url-value="http://a.tumblr.com/tumblr_mirhiitqaC1roewk4o1_r1.mp3" picture-value="https://i.ytimg.com/vi/vAsztnDeZ1Q/maxresdefault.jpg">Demi Lovato &nbsp;∘&nbsp; Heart Attack</div>
    <div class="song" url-value="https://70mack.co/wp-content/upload/2017/10/Davido_FIA.mp3" picture-value="https://3.bp.blogspot.com/-J7w5lyePAfw/WgbF1knkwJI/AAAAAAAAVdI/t2ZOSjmLtssuxuT-czWbETE-hc2DC9wIACK4BGAYYCw/w1200-h630-p-k-no-nu/Davido%2BFia.png"> Davido &nbsp;∘&nbsp; FIA</div>    
    <div class="song" url-value="http://img0.liveinternet.ru/images/attach/b/3/3656/3656927_eminem__mockingbird.mp3" picture-value="https://wallpapercave.com/wp/WlHnNj6.jpg">Eminem &nbsp;∘&nbsp; Mocking Bird</div>    

    </div>


  </div>

</template>

<script>

import { bus } from '../main';

export default {

  name: 'playlist',

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
    changeSource : function(e) {
      let songValue = e.target.attributes[1].value;
      let songImage = e.target.attributes[2].value;
      this.$emit('updateData', [songValue, songImage]);
      bus.$emit('reload');
    }

  }
}

</script>

<style scoped>

#secborder {
    border: 10px solid white;
    border-radius: 15px;
    margin: 2rem 0.5rem;
    background: black;
    height: 35rem;
    width: 40%;
    float: right;
}

.song {
    width: 100%;
    height: 10%;
    padding: 0.5em;
    border-bottom: 0.5px solid #172951;
    font-size: 1.5rem;
    font-weight: bold;
    text-align: center;
    color: white;
    cursor: pointer;
}

</style>
