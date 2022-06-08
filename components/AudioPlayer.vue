<template>
  <div class="player">
    <!-- song details -->
    <h5 id="reproductortext" class="subtitle2">titulo.autor</h5>

    <!-- control buttons -->
    <div class="controls">
      <button class="btn_control" disabled>
        <span class="material-symbols-outlined"><fa :icon="['fas', 'shuffle']" /></span>
      </button>
      <button class="btn_control" disabled>
        <span class="material-symbols-outlined"><fa :icon="['fas', 'angles-left']" /></span>
      </button>
      <button
        class="btn_control playplause"
        @click="playpause">
          <span v-show="!isPlaiying" class="material-symbols-outlined"><fa :icon="['fas', 'play']" /></span>
          <span v-show="isPlaiying" class="material-symbols-outlined"><fa :icon="['fas', 'pause']" /></span>
      </button>
      <button class="btn_control" disabled>
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
margin-left: 20px;
padding: 20px;
color: white;

}
.player{
  background-color: #72B84E;
  height: 200px;
  position: relative;
  bottom: 50px;
  .song_title{
    color: white;
    font-weight: bold;
  }
  .song_author{
    color: white;
    font-size: 0.9em;
  }
  img{
    margin-top: 10px;
  }
  .controls{
    @apply p-2;
    display: flex;
    justify-content: center; 
    .btn_control{
      @apply p-2 w-10 h-10;
      border-radius: 50%;
      background-color: #ddd;

      &.playplause{
        background-color: #72B84E;
        color: white;
        &:hover{
          background: rgb(8,1,122);
          background: linear-gradient(45deg, rgba(8,1,122,1) 0%, rgba(255,0,230,1) 100%);;
          color: white;
        }
      }
      &.repeat{
        &.active{
          background-color: indigo;
          color: white;
        }
        &:hover{
            background: #1A1B37;
            background: #1A1B37;
            color: white;
        }
      }

      &:disabled{
        color: white;

      }
    }
  }
  .progress_bar{
    @apply my-2;
    background-color: white;
    height: 5px;
    width: 100%;
    @apply relative;
    .no_progress{
      @apply h-1 cursor-pointer rounded-full bg-gray-500;
      background-color: gray;
      .progress{
        @apply flex w-full justify-end h-1 rounded-full relative;
        background-color: white;
      }
    }
    .progress_btn_pos{
      @apply flex w-full justify-end h-1 rounded-full relative;
      .progress_btn{
        @apply w-2 h-2 md:w-4 md:h-4  absolute rounded-full shadow;
        background-color: white;
        border: 1px solid #ccc;
        top: -10px;
      }
    }
  }
  .times{
    display: flex;
    justify-content: space-between;
    font-size: 0.8em;
  }
}
</style>
