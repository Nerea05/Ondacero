<template>
  <div class="player">
    <!-- song details -->
    <h5 id="reproductortext" class="subtitle2">After Hours Gema Ruiz </h5>

    <!-- control buttons -->
    <div class="controls">
      <button class="btn_control">
        <span ><fa :icon="['fas', 'shuffle']" /></span>
      </button>
      <button class="btn_control" >
        <span ><fa :icon="['fas', 'angles-left']" /></span>
      </button>
      <button
        class="btn_control playplause"
        @click="playpause">
          <span v-show="!isPlaiying" class="material-symbols-outlined"><fa :icon="['fas', 'play']" /></span>
          <span v-show="isPlaiying" class="material-symbols-outlined"><fa :icon="['fas', 'pause']" /></span>
      </button>
      <button class="btn_control" >
        <span class="material-symbols-outlined"><fa :icon="['fas', 'angles-right']" /></span>
      </button>
      <button
        class="btn_control repeat"
        :class="this.isLooping ? 'active': ''"
        @click="toggleLoop">
        <span class="material-symbols-outlined"><fa :icon="['fas', 'repeat']" /></span>
      </button>
    </div>
    <!-- progress bar -->
    <div class="progress_bar">
      <div
        @click="seek($event)"
        ref="progress"
        class="no_progress">
          <div
            class="progress"
            :style="{'width' : step + '%'}">
          </div>

      </div>
      <div
        class="progress_btn_pos"
        :style="{'width' : step + '%'}">
          <span
            ref="progressbtn"
            id="progressButtonTimer"
            class="progress_btn"></span>
      </div>

    </div>
    <div class="times">
        <div class="start">0:00</div>
        <div class="end">{{song.end}}</div>
    </div>

  </div>
</template>

<script>
import {Howl, Howler} from 'howler';


export default {
  data(){
    return{
      sound: Object,
      isPlaiying: false,
      isLooping: false,
      step: 0,
      song: {
        title: "File example",
        author: "Anonymous",
        src: "/audio.mp3",
        start: 0,
        end: 0
      }
    }
  },
  mounted(){
    this.sound = new Howl({
      src: [this.song.src],
      onload: () => {
        this.song.end = `${Math.round(this.sound._duration/60)}:${Math.round(this.sound._duration)}`;
      }
    });
    this.getTiming();
  },
  methods: {
    playpause(){
      if(this.sound.playing()){
        this.sound.pause();
        this.isPlaiying = false;
      }else{
        this.sound.play();
        this.isPlaiying = true;
      }

    },
    getTiming() {
      setInterval(() => {
        this.updateWidth();
      }, 300)
    },
    updateWidth() {
      if (this.sound.playing()) {
        let width = (this.sound.seek() / this.sound._duration) * 100;
        this.step = Math.round(width);
      }
    },

    toggleLoop(){
      this.isLooping = !this.isLooping;
      this.sound._loop = this.isLooping;
      this.sound._sounds[0]._loop = this.isLooping;
    },

    seek(event){
      const progress = this.$refs.progress;
      let porcent =  event.layerX / progress.clientWidth;

      if (this.sound) {
          if (this.sound.playing()) {
            this.sound.pause();
            this.sound.seek(this.sound._duration * porcent);
            this.sound.play();
            this.step = porcent * 100;
          }else{
            this.sound.seek(this.sound._duration * porcent);
            this.step = porcent * 100;
          }
      }
  }
  }
}
</script>

<style lang="postcss">
#reproductortext{
margin-left: 130px;
padding: 25px;
color: white;
@media only screen and (max-width: 800px){
  color:#72B84E ;
  position: relative;
  left: 30px
}
}

.player{
  background-color: #72B84E;
  height: 200px;
  position: relative;
  bottom: 50px;
  border-top-left-radius: 6%;
  border-top-right-radius: 6%;
  box-shadow: 10px 10px 31px 0px rgba(114,184,78,0.37);
  @media only screen and (max-width: 800px){
  background-color: white;
  box-shadow: none;
  right: 50px
}
  .song_title{
    color: white;
    font-weight: bold;
    @media only screen and (max-width: 800px){
    color: #72B84E;
}
  }
  .song_author{
    color: white;
    font-size: 0.9em;
    @media only screen and (max-width: 800px){
    color: #72B84E;
}
  }
  img{
    margin-top: 10px;
  }
  .controls{
    @apply p-2;
    display: flex;
    justify-content: center; 
    @media only screen and (max-width: 800px){
      position:relative;
      left: 40px;
    }
    .btn_control{
      @apply p-2 w-10 h-10;
      color: white;
      border-radius: 50%;
      @media only screen and (max-width: 800px){
        color: #72B84E;
      }

      &.playplause{
        background-color: #72B84E;
        color: white;
        
        &:hover{
          background: #1A1B37;
          color: white;
        }
      }
      &.repeat{
        &.active{
          color: white;
        }
        &:hover{
            background: #1A1B37;
            color: white;
        }
      }

      &:disabled{
        color: white;
        @media only screen and (max-width: 800px){
          color: #72B84E;
        }
        

      }
    }
  }
  .progress_bar{
    @apply my-2 ml-40;
    background-color: white;
    height: 5px;
    width: 70%;
    @apply relative;
    @media only screen and (max-width: 800px){
    background-color: #72B84E;
    height: 10px;
    position: relative;
    right: 50px;

}
    .no_progress{
      @apply h-1 cursor-pointer rounded-full;
      background-color: white;
      .progress{
        @apply flex w-full justify-end h-1 rounded-full relative;
        background-color: #1A1B37;
      }
    }
    .progress_btn_pos{
      @apply flex w-full justify-end h-1 rounded-full relative;
      .progress_btn{
        @apply w-2 h-2 md:w-4 md:h-4  absolute rounded-full shadow;
        background-color: white;
        top: -10px;
        @media only screen and (max-width: 800px){
          background-color: #1A1B37;
        }
      }
    }
  }
  .times{
    display: flex;
    font-size: 0.8em;
    justify-content: space-around;
    color: white;
    @media only screen and (max-width: 800px){
     color: #72B84E; 
     position: relative;
     left: 40px;    }
  }
}
</style>
